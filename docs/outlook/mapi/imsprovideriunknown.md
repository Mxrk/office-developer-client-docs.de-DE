---
title: IMSProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider
api_type:
- COM
ms.assetid: 0f17aa44-abcb-4732-b013-d91652847cf6
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 9444806347c97077b03922b116e2ed7f61665cc1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792677"
---
# <a name="imsprovider--iunknown"></a>IMSProvider: IUnknown

  
  
**Betrifft**: Outlook 
  
Ermöglicht den Zugriff auf eine Nachricht-Anbieter über eine Nachricht Speicher-Anbieter-Objekt. Dieses Objekt "Message" Speicher-Anbieter wird bei der Anmeldung Anbieter von der Nachricht Informationsdienst [MSProviderInit](msproviderinit.md) Eintrag-Funktion zurückgegeben. Message-Speicher-Anbieter-Objekts wird hauptsächlich von Clientanwendungen und die MAPI-Warteschlange zum Nachrichtenspeicher zu öffnen. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapispi.h  <br/> |
|Verf�gbar gemacht von:  <br/> |Message-Speicher-Anbieter-Objekte  <br/> |
|Implementiert von:  <br/> |Nachricht-Anbieter  <br/> |
|Aufgerufen von:  <br/> |MAPI- und die MAPI-Warteschlange  <br/> |
|Schnittstellenbezeichner:  <br/> |IID_IMSProvider  <br/> |
|Zeigertyp:  <br/> |LPMSPROVIDER  <br/> |
   
## <a name="vtable-order"></a>Vtable-Reihenfolge

|||
|:-----|:-----|
|[Herunterfahren](imsprovider-shutdown.md) <br/> |Schließt einen Anbieter für Nachricht Anmelden in einer bestimmten Reihenfolge.  <br/> |
|[Logon](imsprovider-logon.md) <br/> |Protokolle MAPI an eine Instanz der Anbieter eine Nachricht.  <br/> |
|[SpoolerLogon](imsprovider-spoolerlogon.md) <br/> |Die MAPI-Warteschlange an einen Nachrichtenspeicher protokolliert.  <br/> |
|[CompareStoreIDs](imsprovider-comparestoreids.md) <br/> |Vergleicht zwei e-Mail-Store-Eintragsbezeichner, um zu bestimmen, ob sie auf das gleiche Store-Objekt verweisen.  <br/> |
   
## <a name="remarks"></a>Hinweise

MAPI verwendet einen Speicher-Anbieterobjekt "Message" pro Sitzung, unabhängig davon, wie viele Nachricht Speicher Speicheranbieter geöffnet werden. Wenn eine zweite MAPI-Sitzung anmeldet alle geöffneten Informationsspeicher, ruft MAPI zum Erstellen eines neuen Nachricht Speicher-Anbieter-Objekts für diese Sitzung verwendet ein zweites Mal an **MSProviderInit** . 
  
Ein Objekt "Message" Speicher-Anbieter muss die folgenden ordnungsgemäß funktioniert enthalten:
  
- Ein _LpMalloc_ -Zuweisung von virtuellem Speicher routinemäßige Zeiger für die Verwendung durch alle Speicher, die mit diesem Anbieterobjekt geöffnet. 
    
- Die _LpfAllocateBuffer_, _ LpfAllocateMore _ und _LpfFreeBuffer_ routinemäßige Zeiger auf die Speicherverwaltungsfunktionen [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md)und [MAPIFreeBuffer](mapifreebuffer.md) . 
    
- Eine verknüpfte Liste aller Geschäfte mit diesem Anbieterobjekt geöffnet und noch nicht geschlossen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Schnittstellen](mapi-interfaces.md)

