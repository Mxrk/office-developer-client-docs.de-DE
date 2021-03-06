---
title: Kanonische PidTagDeferredSendUnits-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendUnits
api_type:
- HeaderDef
ms.assetid: 2386be9f-18c9-4949-a2aa-efc8e212801c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 14b1b424bc55a3a8c898eaac386a5344c2e5cf99
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794282"
---
# <a name="pidtagdeferredsendunits-canonical-property"></a>Kanonische PidTagDeferredSendUnits-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt die Zeiteinheit, von denen der Eigenschaftswert **PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) multipliziert werden soll.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_DEFERRED_SEND_UNITS  <br/> |
|Bezeichner:  <br/> |0x3FEC  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |MAPI-status  <br/> |
   
## <a name="remarks"></a>Hinweise

Wenn festgelegt, diese Eigenschaft einen der folgenden Werte aufweisen muss:
  
|||
|:-----|:-----|
|**PidTagDeferredSendUnits** <br/> |Beschreibung  <br/> |
|0  <br/> |Minuten, beispielsweise 60 Sekunden  <br/> |
|1  <br/> |Stunden, beispielsweise 60 x 60 Sekunden  <br/> |
|2  <br/> |Am Tag, beispielsweise 24 x 60 x 60 Sekunden  <br/> |
|3  <br/> |Woche, beispielsweise 7x24x60x60 Sekunden  <br/> |
   
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für e-Mail-Nachrichtenobjekte zulässig sind.
    
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

