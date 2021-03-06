---
title: Kanonische PidTagScheduleInfoFreeBusyTentative-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoFreeBusyTentative
api_type:
- COM
ms.assetid: 28453d29-30c5-405b-84d2-5bb5f281756c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a00505b765abdcb7b8fe9d68052774b30bbdf692
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795103"
---
# <a name="pidtagscheduleinfofreebusytentative-canonical-property"></a>Kanonische PidTagScheduleInfoFreeBusyTentative-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält die Blöcke von Zeiten für die der Frei/Gebucht-Status mit Vorbehalt ist.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_SCHDINFO_FREEBUSY_TENTATIVE  <br/> |
|Bezeichner:  <br/> |0x6852  <br/> |
|Datentyp:  <br/> |PT_MV_BINARY  <br/> |
|Bereich:  <br/> |Frei/Gebucht-Informationen  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft hat viele Werte als die Anzahl von Werten in **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)). Jede Binärwert stellt einen Monat und entspricht dem Wert der selben Index **PR_SCHDINFO_MONTHS_TENTATIVE**. Die binäre Werte werden in der gleichen Reihenfolge wie die Werte in **PR_SCHDINFO_MONTHS_TENTATIVE**sortiert.
  
Jede Binärwert hat mindestens 4-BYTE-Blöcken und einzelnen Elementen durch die Start- und Endzeit in der zweiten zwei Bytes in little-Endian-Format in den ersten beiden Bytes enthält. Die Anfangszeit ist die Anzahl der Minuten zwischen Mitternacht koordinierte Weltzeit (UTC), der den ersten Tag des Monats und die Startzeit des Ereignisses in UTC. Die Endzeit ist die Anzahl der Minuten zwischen den ersten Tag des Monats Mitternacht UTC und Zeit für das Ende des Ereignisses in UTC. Die 4-BYTE-Blöcken werden in aufsteigender Reihenfolge sortiert.
  
Ein Block mit Startzeit als die Anfangszeit des ersten Blocks und Endzeit als Zeit für das Ende des letzten Blocks werden aufeinander folgende oder überlappende Blöcke Zeitraum zusammengeführt. Wenn ein Ereignis über mehrere Monate oder Jahre verteilt ist, wird das Ereignis in mehrere Blöcke, eine pro Monat geteilt. Wenn keine mit Vorbehalt Ereignisse in der Veröffentlichung Bereich vorhanden sind, hat diese Eigenschaft und die **PR_SCHDINFO_MONTHS_TENTATIVE** muss nicht festgelegt werden oder gelöscht werden müssen, wenn sie bereits vorhanden. Andernfalls muss diese Eigenschaft festgelegt werden. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> Veröffentlicht die Verfügbarkeit eines Benutzers oder einer Ressource.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
Mapitags.h
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

