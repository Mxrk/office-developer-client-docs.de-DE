---
title: Kanonische PidLidContactCharacterSet-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactCharacterSet
api_type:
- COM
ms.assetid: a167e199-a9b2-47f9-a90e-2abc7c29828c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 9706d1060347609708070140aae51d9dcadbb9c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793499"
---
# <a name="pidlidcontactcharacterset-canonical-property"></a>Kanonische PidLidContactCharacterSet-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt den Zeichensatz für diesen Kontakt verwendet.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidContactCharSet  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Address  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008023  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Kontakt  <br/> |
   
## <a name="remarks"></a>Hinweise

Anwendungen können diese Eigenschaft verwenden, zur Unterstützung bei der eine Zeichensatz abhängige Liste der Optionen für die **DispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)), **DispidFileUnderList** ([PidLidFileUnderList](pidlidfileunderlist-canonical-property.md)) und **DispidFileUnderId generieren **([PidLidFileUnderId](pidlidfileunderid-canonical-property.md))-Eigenschaften. Wenn der Wert der Eigenschaft "0 x 00000000" oder "0 x 00000001" ist, sollte Applications die-Eigenschaft behandelt, als nicht festgelegt.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für Kontakte und persönliche Verteilerlisten zulässig sind.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

