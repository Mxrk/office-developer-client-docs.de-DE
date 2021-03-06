---
title: Kanonische PidTagSubject-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubject
api_type:
- COM
ms.assetid: aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 63bb5534756f44aebd9e6ca21c336534b279909d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795234"
---
# <a name="pidtagsubject-canonical-property"></a>Kanonische PidTagSubject-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält den vollständigen Betreff einer Nachricht.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_SUBJECT, PR_SUBJECT_A, PR_SUBJECT_W  <br/> |
|Bezeichner:  <br/> |0 x 0037  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |Allgemeine messaging  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften werden für alle Objekte, die Meldung empfohlen. 
  
Diese Eigenschaften sind immer den vollständigen Betreff, d. h., die Verkettung von das Präfix und den normalisierten Betreff. Wenn kein Präfix vorhanden ist, sollte der normalisierte Betreff den Betreff identisch sein. Eine Nachricht speichern oder transport-Anbieter verwendet, die diese Eigenschaften und die Eigenschaften zum Berechnen des normalisierten Betreffs mithilfe der Regel **PR_SUBJECT_PREFIX** ([PidTagSubjectPrefix](pidtagsubjectprefix-canonical-property.md)) unter **PR_NORMALIZED_SUBJECT** ([ beschrieben PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md)).
  
Die Subject-Eigenschaften in der Regel kleine Zeichenfolgen von weniger als 256 Zeichen sind, und eine Nachricht Speicheranbieter ist nicht verpflichtet, klicken sie auf die **IStream** -Schnittstelle unterstützt. Der Client sollte immer Zugriff über die Schnittstelle **IMAPIProp** zuerst versuchen, und greifen auf **IStream** nur, wenn **MAPI_E_NOT_ENOUGH_MEMORY** zurückgegeben wird. 
  
Für einen Bericht enthält diese Eigenschaft die ursprüngliche Nachricht Betreff eine Zeichenfolge, die angibt, wo der Nachricht vorangestellt.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Nachrichten und Anlagen Objekte behandelt.
    
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

