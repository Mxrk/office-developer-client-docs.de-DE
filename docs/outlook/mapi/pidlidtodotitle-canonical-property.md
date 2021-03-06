---
title: Kanonische PidLidToDoTitle-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidToDoTitle
api_type:
- COM
ms.assetid: 94cf031f-4c78-441d-9c01-55905b4974e0
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 66208b2d31ca379389f3249abf281dd4d040e276
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793879"
---
# <a name="pidlidtodotitle-canonical-property"></a>Kanonische PidLidToDoTitle-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält Benutzer festzulegen Text, um dieses Objekt "Message" in einer konsolidierten Vorgangsliste zu ermitteln.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidToDoTitle  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Common  <br/> |
|Long-ID (Abdeckung):  <br/> |0x000085A4  <br/> |
|Datentyp:  <br/> |PT_UNICODE  <br/> |
|Bereich:  <br/> |Aufgabe  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft muss auf eine Aufgabe nicht festgelegt werden. Um eine leere Eigenschaft anzugeben, legen Sie diese Eigenschaft nicht auf die leere Zeichenfolge, aber stattdessen zu löschen. 
  
Beim Kennzeichnen von einem Message-Objekt und die Eigenschaft nicht vorhanden ist, sollte den Wert der **PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)) ein Client auf diese Eigenschaft geschrieben werden.
  
In einer konsolidierten Vorgangsliste Wenn diese Eigenschaft nicht vorhanden ist, sollten ein Client den Wert der Eigenschaft **PR_NORMALIZED_SUBJECT** ersetzen, wenn diese Eigenschaft in der Vorgangsliste anzeigen. 
  
Auf ein Objekt "Message" Entwurf Wenn der Client Absender Flags, die implementiert sollte diese Eigenschaft werden auf denselben Wert als **DispidRequest** ([PidLidFlagRequest](pidlidflagrequest-canonical-property.md)) festgelegt.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen
    
[[MS-OXOFLAG]](http://msdn.microsoft.com/library/f1e50be4-ed30-4c2a-b5cb-8ff3aaaf9b91%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge im Zusammenhang mit kennzeichnen.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[Kanonische PidTagNormalizedSubject-Eigenschaft](pidtagnormalizedsubject-canonical-property.md)
  
[Kanonische PidLidFlagRequest-Eigenschaft](pidlidflagrequest-canonical-property.md)


[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

