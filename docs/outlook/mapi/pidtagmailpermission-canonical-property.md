---
title: Kanonische PidTagMailPermission-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMailPermission
api_type:
- HeaderDef
ms.assetid: f8270ef2-56d4-4b47-bdda-a39c966bbcba
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 4cc97647c60322783050abbebd18726434632a43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794583"
---
# <a name="pidtagmailpermission-canonical-property"></a>Kanonische PidTagMailPermission-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält True, wenn der messaging-Benutzer senden und Empfangen von Nachrichten zulässig ist. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_MAIL_PERMISSION  <br/> |
|Bezeichner:  <br/> |0x3A0E  <br/> |
|Datentyp:  <br/> |PT_BOOLEAN  <br/> |
|Bereich:  <br/> |Adresse  <br/> |
   
## <a name="remarks"></a>Hinweise

Wenn diese Eigenschaft nicht festgelegt ist, wird Sie MAPI wie mit dem Wert TRUE behandelt. 
  
Legen Sie diese Eigenschaft auf false festgelegt, in ein Unternehmensverzeichnis, wo sind einige der Einträge nicht e-Mail-aktivierte. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

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

