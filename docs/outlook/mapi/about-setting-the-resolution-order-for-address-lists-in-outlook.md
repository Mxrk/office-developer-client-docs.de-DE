---
title: Informationen zum Festlegen der L�sung Reihenfolge f�r Adresslisten in Outlook
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1589568-cb49-86dd-5d16-b08c8117bd17
description: 'Letzte �nderung: Donnerstag, 5. Juli 2012'
ms.openlocfilehash: cfc640fd419ad030de6922fa61817881caa70d07
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791219"
---
# <a name="about-setting-the-resolution-order-for-address-lists-in-outlook"></a>Informationen zum Festlegen der L�sung Reihenfolge f�r Adresslisten in Outlook

  
  
**Betrifft**: Outlook 
  
Für jedes Profil Microsoft Office Outlook unterstützt mehrere Adresslisten, und Benutzer können die Reihenfolge der Adresslisten, die von der, die Empfänger in e-Mail-Nachrichten und Teilnehmer in Besprechungsanfragen aufgelöst werden manuell angeben. Beispielsweise k�nnen Sie die Reihenfolge der L�sung festlegen, sodass Namen aufgel�st zuerst gegen Ihr Outlook-Adressbuch, und klicken Sie dann der globalen Adressliste enthalten sind. Auf einem Computer ein Benutzer im Adressbuch �ffnen, klicken Sie auf **Extras** und dann auf **Optionen**, um diesen Auftrag L�sung anzugeben. Es ist jedoch in einer Unternehmensumgebung effizienter f�r IT-Administratoren die Reihenfolge der Adresslisten programmgesteuert festgelegt mit dem Namen aufgel�st werden. Diese Art von Code kann als Teil eines Skripts zum Starten Automation verwendet werden, die von ein Administrator innerhalb des Unternehmens bereitgestellt. 
  
MAPI unterst�tzt die **[SetSearchPath](iaddrbook-getsearchpath.md)** -Methode in die **[IAddrBook](iaddrbookimapiprop.md)** -Schnittstelle k�nnen Sie einen neuen Pfad f�r die Suche im Profil festlegen, die f�r die Namensaufl�sung verwendet wird. Wie die **IAddrBook::SetSearchPath** -Methode verwenden, m�ssen Sie angeben, auf die gew�nschte Aufl�sung Reihenfolge unter Verwendung eines Arrays, das Container f�r die entsprechende Adresse enth�lt in der Reihenfolge von Adressb�chern, die sie gel�st werden sollen. Jeder Eintrag in diesem Array sollte auch die Eintrags-ID des entsprechenden Adressbuch enthalten. 
  
Es folgen Beispiele daf�r, wie Sie eine benutzerdefinierte Suchpfad f�r Adresslisten an Code.
  
- [Die Reihenfolge der Lösung für Adresslisten programmgesteuert festlegen](how-to-programmatically-set-the-resolution-order-for-address-lists.md)
    
- [KB 292590: zum �ndern der Address Book Sortierreihenfolge mit SetSearchPath](http://support.microsoft.com/kb/292590)
    

