---
title: Kanonische PidLidAppointmentStateFlags-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAppointmentStateFlags
api_type:
- COM
ms.assetid: 1e5f0f83-c40b-4b3a-8492-61d1b53b1e3c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 293eb489a1e926f0e60e823a536dacf6f409e353
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793428"
---
# <a name="pidlidappointmentstateflags-canonical-property"></a>Kanonische PidLidAppointmentStateFlags-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt ein Bitfeld, das den Status des Objekts beschreibt.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidApptStateFlags  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Appointment  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008217  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Besprechungen  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft ist nicht erforderlich. Im folgenden sind die einzelnen Flags, die festgelegt werden können.
  
M (AsfMeeting, 0 x 00000001)
  
> Dieses Kennzeichen gibt an, dass das Objekt einer Besprechung oder bezüglich Besprechungen-Objekts ist.
    
R (AsfReceived, 0 x 00000002)
  
> Dieses Kennzeichen gibt an, dass das dargestellte Objekt aus einer anderen Person empfangen wurde.
    
C (AsfCanceled, 0 x 00000004)
  
> Dieses Kennzeichen gibt an, dass das Besprechung-Objekt, das durch das Objekt dargestellten abgebrochen wurde.
    
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

