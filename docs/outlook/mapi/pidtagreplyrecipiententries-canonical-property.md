---
title: Kanonische PidTagReplyRecipientEntries-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReplyRecipientEntries
api_type:
- COM
ms.assetid: a903fd22-a3f2-464f-99b0-c087e211b124
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 1ab8828dd2fc28a2fba1620fc251ba0a87c3e2bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794953"
---
# <a name="pidtagreplyrecipiententries-canonical-property"></a>Kanonische PidTagReplyRecipientEntries-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält eine Größe Array von Eintragsbezeichner für Empfänger, die eine Antwort erhalten.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_REPLY_RECIPIENT_ENTRIES  <br/> |
|Bezeichner:  <br/> |0x004F  <br/> |
|Datentyp:  <br/> |PT_BINARY  <br/> |
|Bereich:  <br/> |MAPI-Umschlag  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft enthält eine [FLATENTRYLIST](flatentrylist.md) -Struktur und ist keine mehrwertige Eigenschaft. 
  
Wenn diese Eigenschaft nicht vorhanden ist, wird nur für den Benutzer durch die **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md))-Eigenschaft identifiziert eine Antwort gesendet. Wenn dies und **PR_REPLY_RECIPIENT_NAMES** ([PidTagReplyRecipientNames](pidtagreplyrecipientnames-canonical-property.md))-Eigenschaften definiert sind, wird die Antwort an alle diese beiden Eigenschaften identifizierten Empfänger gesendet. Ein Transportdienstes verwendet diese Eigenschaften die Logik üblichen Antworten außer Kraft gesetzt.
  
Wenn diese Eigenschaft oder die **PR_REPLY_RECIPIENT_NAMES** -Eigenschaft festgelegt ist, muss auch die anderen-Eigenschaft festgelegt werden. Diese Eigenschaften müssen die gleiche Anzahl von Empfängern enthalten, und sie müssen in der gleichen Reihenfolge enthalten. Installationsfehler, diese Anforderungen zu beobachten kann zu unvorhersehbaren Ergebnissen führen. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für e-Mail-Nachrichten zulässig sind.
    
[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> Konvertiert von Internet-standard-e-Mail-Konventionen in Message-Objekten.
    
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

