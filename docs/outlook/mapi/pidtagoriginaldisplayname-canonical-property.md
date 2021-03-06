---
title: Kanonische PidTagOriginalDisplayName-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayName
api_type:
- COM
ms.assetid: 176245d9-724d-44f1-b7a3-eddf652533b2
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 4a43bc33f13d8325a55d09b5ef3031dc632cf587
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794682"
---
# <a name="pidtagoriginaldisplayname-canonical-property"></a>Kanonische PidTagOriginalDisplayName-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält den ursprünglichen Anzeigenamen für einen Eintrag aus einem Adressbuch in ein persönliches Adressbuch oder anderen beschreibbaren des Adressbuchs kopiert.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_ORIGINAL_DISPLAY_NAME, PR_ORIGINAL_DISPLAY_NAME_A, PR_ORIGINAL_DISPLAY_NAME_W  <br/> |
|Bezeichner:  <br/> |0x3A13  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |Allgemeine messaging  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften enthalten Informationen zu der ursprünglichen Quelle des kopierten-Eintrags.
  
Bei einem Bericht nonread enthalten diese Eigenschaften eine Kopie des Anzeigenamens von der ursprünglichen Empfänger der Nachricht für den der Bericht generiert wird. Wenn Sie der ursprüngliche Empfänger einer Verteilerliste gehört, wird der Anzeigename der Verteilerliste für den Bericht beibehalten.
  
Diese Eigenschaften können eine Clientanwendung um Änderung oder "spoofing" von Einträgen, zu verhindern, indem Sie eine unveränderte Kopie des Anzeigenamens zum Vergleichen von eigenständigen erteilen.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen für Listen der Benutzer, Kontakte, Gruppen und Ressourcen.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
Mapitags.h
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[Kanonische PidTagTransmittableDisplayName-Eigenschaft](pidtagtransmittabledisplayname-canonical-property.md)


[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

