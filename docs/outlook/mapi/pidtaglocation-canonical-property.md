---
title: Kanonische PidTagLocation-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLocation
api_type:
- HeaderDef
ms.assetid: 99dffcd9-83dc-462e-b0ce-e2101e546cc6
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 03082536902ead880ba88343cd1991e518ed5665
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794578"
---
# <a name="pidtaglocation-canonical-property"></a>Kanonische PidTagLocation-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält den Speicherort des Empfängers in einem Format, die in der Aufgabenliste des Empfängers Organisation eignet. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_LOCATION, PR_LOCATION_A, PR_LOCATION_W  <br/> |
|Bezeichner:  <br/> |0x3A0D  <br/> |
|Datentyp:  <br/> |PT_UNICODE PT_STRING8  <br/> |
|Bereich:  <br/> |Adresse  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften Identitätsnachweis und Zugriff auf Informationen für einen Empfänger. Sie sind durch den Empfänger und ihre Organisation definiert. 
  
Die Inhalte werden durch die Anforderungen der Organisation des Empfängers definiert. Einige Organisationen möglicherweise beispielsweise messaging-Benutzer identifizieren, durch das Erstellen von Anzahl und die geschäftliche Rufnummer angeben. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für Kontakte und persönliche Verteilerlisten zulässig sind.
    
[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen für Listen der Benutzer, Kontakte, Gruppen und Ressourcen.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
Mapitags.h
  
> Enthält Definitionen von Eigenschaften, die als zugeordneten Eigenschaften aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

