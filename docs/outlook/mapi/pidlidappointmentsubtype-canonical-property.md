---
title: Kanonische PidLidAppointmentSubType-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentSubType
api_type:
- COM
ms.assetid: e2e00af3-1fb3-4314-936a-f480674d3d83
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: cb9f4e0f58ea27d36ba911ed60527a2e53f23727
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793427"
---
# <a name="pidlidappointmentsubtype-canonical-property"></a>Kanonische PidLidAppointmentSubType-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt an, ob das Ereignis den ganzen Tag ist.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidApptSubType  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Appointment  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008215  <br/> |
|Datentyp:  <br/> |PT_BOOLEAN  <br/> |
|Bereich:  <br/> |Kalender  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft gibt an, ob das Ereignis ein ganztägiges Ereignis, wie vom Benutzer angegeben ist oder nicht. Der Wert gibt TRUE an, dass das Ereignis als ganztägiges Ereignis in diesem Fall müssen der Start- und Endzeit Mitternacht sein ist, damit die Dauer ein Vielfaches von 24 Stunden ist und mindestens 24 Stunden ist. Den Wert FALSE oder Abwesenheit dieser Eigenschaft wird angegeben, dass das Ereignis nicht um ein ganztägiges Ereignis ist. Der Client oder Server müssen Sie nicht den Wert true ableiten, wenn ein Benutzer ein Ereignis zu erstellen, ist von 24 Stunden, geschieht, auch wenn das Ereignis beginnt und um Mitternacht endet.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für den Termin, einer Besprechungsanfrage und Antwortnachrichten.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

