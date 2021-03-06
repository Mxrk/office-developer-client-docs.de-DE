---
title: Nachricht Empfang Modell
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d85d269e-2251-4399-9159-a2f47a85e3d1
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: cecdb2c30d6c9df2aafbeed43714269b863ebc48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19793257"
---
# <a name="message-reception-model"></a>Nachricht Empfang Modell

  
  
**Betrifft**: Outlook 
  
Der Adressbuchhierarchie steuert, ob die MAPI-Warteschlange es für eingehende e-Mails Fragen muss oder führt gibt an, ob ein Rückruf an die Warteschlange MAPI, wenn neue Nachrichten eingehen. Beenden von [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) Abruf anfordern, legt der Transportdienst SP_LOGON_POLL-Flag. Andernfalls wird der Adressbuchhierarchie [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) verwendet, wenn eingehende e-Mails verfügbar ist. Nach dem Learning, dass eingehende e-Mails verfügbar ist, die MAPI-Warteschlange öffnet eine neue Nachricht und fordert der Adressbuchhierarchie zum Speichern von empfangenen Nachrichteneigenschaften in die Nachricht an. 
  
Dieser Prozess funktioniert folgendermaßen:
  
1. Verfügbare Nachrichten werden durch entweder der Adressbuchhierarchie Aufrufen **IMAPISupport::SpoolerNotify** oder durch die MAPI-Warteschlange aufrufen [IXPLogon::Poll](ixplogon-poll.md)angegeben.
    
2. Die MAPI-Warteschlange ruft [IXPLogon::StartMessage](ixplogon-startmessage.md) , um den Vorgang zu initiieren. 
    
3. Der Adressbuchhierarchie Fügt einen Verweiswert an der Position, die in **StartMessage**verwiesen wird. Diese Referenzwerte zulassen der Adressbuchhierarchie und die MAPI-Warteschlange zum Nachverfolgen der Nachricht verarbeitet wird, wenn mehrere Nachrichten übermitteln vorhanden sind.
    
4. Der Transportdienst speichert die Daten der Nachricht in den übergebenen [IMessage: IMAPIProp](imessageimapiprop.md) Instanz. 
    
5. Der Transportdienst Ruft die [IMAPIProp::SaveChanges](imapiprop-savechanges.md) -Methode für die Instanz **IMessage** und gibt **StartMessage**zurück.
    
6. Die MAPI-Warteschlange [IXPLogon::TransportNotify](ixplogon-transportnotify.md) aufgerufen, wenn Nachrichtenübermittlung beendet werden muss. 
    
> [!NOTE]
> Wenn ein Transportdienstes eine große Anzahl von Nachrichten übermitteln muss und der Adressbuchhierarchie **IMAPISupport::SpoolerNotify** anstelle von **IXPLogon::Poll**, sollte darauf geachtet werden nicht zum Aufrufen **SpoolerNotify** zu häufig dagegen in Reihenfolge Entzieht andere Transportanbieter der CPU-Zeit. Die MAPI-Warteschlange hat Logik für diesen Fehler zu vermeiden, aber im Allgemeinen sollten das Intervall zwischen Aufrufen **SpoolerNotify** länger als die benötigte Zeit Ihrer Adressbuchhierarchie eine Nachricht verarbeitet werden. > Darüber hinaus kann die MAPI-Warteschlange eine eingehende Nachricht nicht sofort verarbeitet. Die MAPI-Warteschlange beantragen der Adressbuchhierarchie für andere Aufgaben, bevor er die eingehende Nachricht empfängt. 
  

