---
title: Kanonische PidTagUrlComponentName-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUrlComponentName
api_type:
- COM
ms.assetid: a21906f9-5408-41ba-a89b-273ab60eeef3
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 3a2b0939bbfa5143e4bd99e74b0f84e3ca7efb12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795282"
---
# <a name="pidtagurlcomponentname-canonical-property"></a>Kanonische PidTagUrlComponentName-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Der URL-Name der Komponente für eine Nachricht. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_URL_COMP_NAME, PR_URL_COMP_NAME_A, PR_URL_COMP_NAME_W  <br/> |
|Bezeichner:  <br/> |0x10F3  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |Allgemeine messaging  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften sollten innerhalb eines Ordners eindeutig sein. Wenn dies nicht festgelegt, wenn die Nachricht erstellt wird, sollte der Nachrichtenspeicher diese Eigenschaften basierend auf verschiedenen Nachrichteneigenschaften, abhängig von der Nachrichtenklasse festgelegt. Beispielsweise die **IPM. Hinweis** und **IPM. Termin** Nachrichten sollten diese Eigenschaft auf Basis der **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))-Eigenschaft und die **IPM festgelegt haben. Kontakt** Nachrichten sollten diese Eigenschaft basierend auf der **DispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md))-Eigenschaft festgelegt haben. Für die meisten anderen Nachrichtenklassen sollte diese Eigenschaft auf die Eigenschaft **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) basieren.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Nachrichten und Anlagen Objekte behandelt.
    
[[MS-OXTNEF]](http://msdn.microsoft.com/library/1f0544d7-30b7-4194-b58f-adc82f3763bb%28Office.15%29.aspx)
  
> Codiert und decodiert Nachrichten- und Objekte, die auf eine effiziente Streamdarstellung.
    
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

