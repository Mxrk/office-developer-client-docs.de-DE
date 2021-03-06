---
title: Kanonische PidTagFormHostMap-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFormHostMap
api_type:
- HeaderDef
ms.assetid: 92742747-cce0-4c54-9ece-1fcf652ac498
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 9e0316ead2adf00619bd87c57946ba72ed01f4b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794416"
---
# <a name="pidtagformhostmap-canonical-property"></a>Kanonische PidTagFormHostMap-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält eine Zuordnung Host der verfügbaren Formulare. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_FORM_HOST_MAP  <br/> |
|Bezeichner:  <br/> |0x3306  <br/> |
|Datentyp:  <br/> |PT_MV_LONG  <br/> |
|Bereich:  <br/> |Allgemeine MAPI  <br/> |
   
## <a name="remarks"></a>Hinweise

Eine Clientanwendung sollten diese Eigenschaft zusammen mit der Eigenschaft **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) aktualisieren, beim Ändern die Struktur der zugrunde liegenden in der **IMAPIFormProp** -Schnittstelle. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

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

