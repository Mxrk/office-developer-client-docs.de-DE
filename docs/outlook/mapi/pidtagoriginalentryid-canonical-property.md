---
title: Kanonische PidTagOriginalEntryId-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalEntryId
api_type:
- COM
ms.assetid: 8197d2c7-8665-41b8-bd3a-e9c1c2e642e9
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: d60531b087d00ca63a060a4dbfac559ba3b01788
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794698"
---
# <a name="pidtagoriginalentryid-canonical-property"></a>Kanonische PidTagOriginalEntryId-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält die ursprünglichen Eintrags-ID für einen Eintrag aus einem Adressbuch an ein persönliches Adressbuch oder anderen beschreibbaren Adressbuch kopiert.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_ORIGINAL_ENTRYID  <br/> |
|Bezeichner:  <br/> |0x3A12  <br/> |
|Datentyp:  <br/> |PT_BINARY  <br/> |
|Bereich:  <br/> |Allgemeine messaging  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft ist eine der Eigenschaften, die der ursprünglichen Quelle eines Eintrags kopierten Informationen enthalten.
  
Bei einem Bericht nonread enthält diese Eigenschaft eine Kopie des Eintrags-ID von der ursprünglichen Empfänger der Nachricht für den der Bericht generiert wird. Wenn Sie der ursprüngliche Empfänger einer Verteilerliste gehört, wird die Eintrags-ID der Verteilerliste für den Bericht beibehalten.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen für Listen der Benutzer, Kontakte, Gruppen und Ressourcen.
    
[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> Synchronisieren von messaging Objektdaten zwischen einem Server und einem Client behandelt.
    
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

