---
title: Kanonische PidTagResourcePath-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourcePath
api_type:
- COM
ms.assetid: ac49538e-6ee8-4ab4-9d79-88a83c7d0149
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: d7385ea403e7ea45c97f6fd98e422ad7eb762c4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794981"
---
# <a name="pidtagresourcepath-canonical-property"></a>Kanonische PidTagResourcePath-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Einen Pfad zu den Dienstanbieter Server enthält.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_RESOURCE_PATH, PR_RESOURCE_PATH_A, PR_RESOURCE_PATH_W  <br/> |
|Bezeichner:  <br/> |0x3E07  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |MAPI-status  <br/> |
   
## <a name="remarks"></a>Hinweise

Der Pfad in diesen Eigenschaften enthalten stellt den vorgeschlagenen Pfad, in dem der Benutzer Ressourcen suchen kann. Die Definition dieser Eigenschaften ist anbieterspezifisch. Beispielsweise verwendet eine Anwendung zur terminplanung diese Eigenschaften, um den vorgeschlagenen Speicherort für die Planung Anwendungsdateien anzugeben.
  
Das messaging Benutzerprofil stellt diese Eigenschaften Komfort bereit, damit eine Clientanwendung nicht den messaging-Benutzer für ein Netzwerkpfad oder Laufwerkbuchstabens auffordern.
  
MAPI funktioniert nur mit Dateinamen in den Zeichensatz amerikanischen National Standards Institute (ANSI). Anwendungen, die Dateinamen in einem Zeichensatz OEM (Original Equipment Manufacturer) verwenden, müssen diese in ANSI konvertieren, vor dem Aufruf von MAPI.
  
## <a name="related-resources"></a>Verwandte Ressourcen

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

