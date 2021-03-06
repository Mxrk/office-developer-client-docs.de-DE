---
title: Downloadstatus-Tabelle
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 5bcc8b0a-0ab7-6c3e-8334-9e83cf2882a7
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 6a29cc131b4fe352b067e343376b2b705e8e3244
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791596"
---
# <a name="download-table-state"></a>Downloadstatus-Tabelle

  
  
**Betrifft**: Outlook 
  
 In diesem Thema wird beschrieben, während der Tabelle Downloadstatus von der Replikation Zustandsautomat erläutert. 
  
## <a name="quick-info"></a>QuickInfo

|||
|:-----|:-----|
|State-ID:  <br/> |**LR_SYNC_DOWNLOAD_TABLE** <br/> |
|Verwandte-Datenstruktur:  <br/> |**[DNTBL](dntbl.md)** <br/> |
|Aus diesem Zustand:  <br/> |[Synchronisieren von Inhalt Zustand](synchronize-contents-state.md) <br/> |
|Diesen Status:  <br/> |Synchronisieren von Inhalt Zustand  <br/> |
   
> [!NOTE]
> Das Zustandsautomat Replikation ist ein deterministisch Zustandsautomat. Ein Client, der von einem Zustand zu einem anderen Unternehmen muss schließlich auf die frühere letztere zurückgeben. 
  
## <a name="description"></a>Beschreibung

Dieser Status wird initiiert, einen Ordner herunterladen. Während dieser Zustand initialisiert Outlook die zugeordnete **DNTBL** -Datenstruktur mit Informationen zu den Ordner. Der Client den Ordnerinhalt downloads und aktualisiert den Ordner auf dem lokalen Speicher mit neuen Inhalt, geändert oder vom Server gelöscht. Der Downloadvorgang nimmt Microsoft Exchange inkrementelle Änderung Synchronisierung (ICS). Weitere Informationen zu ICS finden Sie unter [ICS Bewertungskriterien](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).
  
Wenn dieser Status beendet ist, gibt der lokale Speicher auf den Status der Synchronize-Inhalt zurück.
  
## <a name="see-also"></a>Siehe auch



[Über die API-Replikation](about-the-replication-api.md)
  
[MAPI-Konstanten](mapi-constants.md)
  
[Informationen zu den Replikationsstatus Computer](about-the-replication-state-machine.md)
  
[SYNCHRONISIERUNGSSTATUS](syncstate.md)

