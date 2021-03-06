---
title: Kanonische PidTagSelectable-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSelectable
api_type:
- COM
ms.assetid: eeecd957-dd50-4849-9698-8bc7106301e9
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 225c435107ba79183c737ddb8e09cda1ffbd83f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795119"
---
# <a name="pidtagselectable-canonical-property"></a>Kanonische PidTagSelectable-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält True, wenn der Eintrag in der einmaligen Tabelle ausgewählt werden kann. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_SELECTABLE  <br/> |
|Bezeichner:  <br/> |0x3609  <br/> |
|Datentyp:  <br/> |PT_BOOLEAN  <br/> |
|Bereich:  <br/> |Adressbuchcontainer  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft wird in erster Linie für die visuelle Formatierung einer einmaligen Tabelle verwendet. Vorlagen können, indem Sie einen Eintrag, der angibt, die Überschrift für die Gruppe erstellen gruppiert werden. Durch Festlegen dieser Eigenschaft auf false festgelegt, für die Überschrift wird sichergestellt, dass der Benutzer nur die eigentlichen Vorlagen in der Gruppe und nicht bei diesem Eintrag Überschrift auswählen kann. 
  
Diese Eigenschaft gilt nur für einer einmaligen Tabelle, nicht zu einer Address Book Hierarchie-Tabelle. 
  
MAPI ermöglicht eine Adressbuchanbieter zum Gruppieren von Elementen visuell durch zweierlei. Erstens können bestimmte Zeilen als Überschriften fungieren, werden Sie nicht ausgewählt. Zweitens können die auswählbaren Elemente relativ zu ihrer Überschriften mithilfe der **PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))-Eigenschaft eingezogen werden. Diese Eigenschaft wird in solchen Gruppierung verwendet, um anzugeben, ob dieses Element aus einer Liste zum Erstellen eines einmaligen ausgewählt werden kann oder nicht. Beispielsweise wenn ein Client mehrere Vorlagen zum Erstellen von Faxadressen verfügt, können sie wie folgt angezeigt: 
  
FAX-Vorlagen (Tiefe 0, nicht ausgewählt werden kann)
  
 Lokale (Tiefe 1, auswählbar) 
  
 Ferngespräche (Tiefe 1, auswählbar) 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOABKT]](http://msdn.microsoft.com/library/cd5a3e78-1eeb-4a75-88eb-e82c8c96ff31%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für Address Book Vorlagen zulässig sind.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
Mapitags.h
  
> Enthält Definitionen von Eigenschaften, die als zugeordneten Eigenschaften aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[GetOneOffTable](iablogon-getoneofftable.md)
  
[Kanonische PidTagFolderType-Eigenschaft](pidtagfoldertype-canonical-property.md)


[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

