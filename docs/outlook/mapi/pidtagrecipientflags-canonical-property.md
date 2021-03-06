---
title: Kanonische PidTagRecipientFlags-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientFlags
api_type:
- COM
ms.assetid: 9fbe537f-b5fe-48a2-803c-653c50c82efd
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a93e5a44768cd99512189f800bf98ab6e30b575d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794894"
---
# <a name="pidtagrecipientflags-canonical-property"></a>Kanonische PidTagRecipientFlags-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt ein Bitfeld, das der Empfängerstatus beschreibt.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_RECIPIENT_FLAGS  <br/> |
|Bezeichner:  <br/> |0x5FFD  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Transport-Empfänger  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft ist nicht erforderlich. Im folgenden werden die einzelnen Flags, die festgelegt werden können.
  
|**Wert**|**Beschreibung**|
|:-----|:-----|
|S (RecipSendable, 0 x 00000001)  <br/> |Der Empfänger ist ein **Sendable** Teilnehmer. Dieses Kennzeichen werden nur in der Eigenschaft **DispidApptUnsendableRecips** ([PidLidAppointmentUnsendableRecipients](pidlidappointmentunsendablerecipients-canonical-property.md)) verwendet.  <br/> |
|O (RecipOrganizer 0x0000002)  <br/> |Die **RecipientRow** , auf denen dieses Flag festgelegt ist, stellt den Besprechungsorganisator.  <br/> |
|ER (RecipExceptionalResponse, 0 x 00000010)  <br/> |Gibt an, dass der Teilnehmer für die Ausnahme eine Antwort gesendet hat in der sich diese **RecipientRow** befindet. Dieses Kennzeichen werden nur in einer **RecipientRow** eines Objekts eingebettete Nachricht Ausnahme vom Organisator der Besprechung-Objekts verwendet.  <br/> |
|ED (RecipExceptionalDeleted, 0 x 00000020)  <br/> |Gibt an, dass zwar die **RecipientRow** vorhanden ist, es behandelt werden soll, als ob der entsprechende Empfänger nicht der Fall ist. Dieses Kennzeichen werden nur in einer **RecipientRow** eines Objekts eingebettete Nachricht Ausnahme vom Organisator der Besprechung-Objekts verwendet.  <br/> |
|X (reserviert, 0 x 00000040)  <br/> |Muss nicht festgelegt werden.  <br/> |
|X (reserviert, 0x00000080)  <br/> |Muss nicht festgelegt werden.  <br/> |
|G (RecipOriginal, 0 x 00000100)  <br/> |Gibt an, dass der Empfänger ursprünglichen teilnimmt. Dieses Kennzeichen werden nur in der **DispidApptUnsendableRecips** -Eigenschaft verwendet.  <br/> |
|X (reserviert, 0 x 00000200)  <br/> |Reserviert.  <br/> |
   
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für den Termin, einer Besprechungsanfrage und Antwortnachrichten.
    
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

