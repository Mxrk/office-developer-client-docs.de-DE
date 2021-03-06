---
title: Kanonische PidTagTitle-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTitle
api_type:
- COM
ms.assetid: f35bbcc3-15dd-40ab-9bf4-bdb21f95d464
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 825922bec95a24fe718cdb7db82851a820c364ad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795250"
---
# <a name="pidtagtitle-canonical-property"></a>Kanonische PidTagTitle-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält die Position des Empfängers.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_TITLE, PR_TITLE_A, PR_TITLE_W  <br/> |
|Bezeichner:  <br/> |0x3A17  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |MAPI-e-Mail-Benutzer  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften Identitätsnachweis und Zugriff auf Informationen für einen Empfänger. Sie sind durch den Empfänger und des Empfängers Organisation definiert. 
  
Diese Eigenschaften werden häufig verwendet, des Empfängers formelle Position, wie beispielsweise Senior Programmierer, statt berufliche-Klasse, wie Programmierer an. Es wird nicht in der Regel für Titel wie eines Unternehmens? "Suffix" verwendet oder DDS.
  
Allgemeine Werte für diese Eigenschaft sind: Managing Director, Programmierer II, Dozenten zuordnen und leitender Softwareentwickler. 
  
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
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

