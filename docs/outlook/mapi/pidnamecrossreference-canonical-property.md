---
title: Kanonische PidNameCrossReference-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidNameCrossReference
api_type:
- COM
ms.assetid: d16e1adf-c911-427e-9c98-678a303e6791
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 148d71dc0e99e23ffe10445068170617cb26b01b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793972"
---
# <a name="pidnamecrossreference-canonical-property"></a>Kanonische PidNameCrossReference-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält einen [RFC3282] Xref Kopfzeile der Wert des Felds.
  
|||
|:-----|:-----|
|Anzeigenamen:  <br/> |Keine  <br/> |
|-Eigenschaft festgelegt:  <br/> |PS_INTERNET_HEADERS  <br/> |
|Name der Eigenschaft:  <br/> |XRef  <br/> |
|Datentyp:  <br/> |PT_UNICODE  <br/> |
|Bereich:  <br/> |E-Mail  <br/> |
   
## <a name="remarks"></a>Hinweise

Um den Wert dieser Eigenschaft festzulegen, müssen den gewünschten Wert Multipurpose Internet Message Extensions (MIME)-Clients in einer XRef Kopfzeilenfeld geschrieben werden. MIME-Leser müssen auf den Wert dieser Eigenschaft den Wert eines Felds Kopfzeile XRef kopieren.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> Konvertiert von Internet-standard-e-Mail-Konventionen in Message-Objekten.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

