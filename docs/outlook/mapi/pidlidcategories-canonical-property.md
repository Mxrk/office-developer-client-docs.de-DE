---
title: Kanonische PidLidCategories-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCategories
api_type:
- COM
ms.assetid: 6ad2aedc-405b-475e-ac76-7ecbbef28f73
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 01d4391850067d00645b5c0248e1bf858c2a9049
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793463"
---
# <a name="pidlidcategories-canonical-property"></a>Kanonische PidLidCategories-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt eine Liste der Kategorien für ein Element.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidCategories  <br/> |
|-Eigenschaft festgelegt:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00002328  <br/> |
|Datentyp:  <br/> |PT_MV_UNICODE  <br/> |
|Bereich:  <br/> |Common  <br/> |
   
## <a name="remarks"></a>Hinweise

Um ein Kopfzeilenfeld Schlüsselwörter generiert werden soll, müssen die Clients den Wert dieser Eigenschaft auf die gewünschten Werte festgelegt. Diese Eigenschaft hat mehrere Zeichenfolgen. jeder Kategorie sollte zu einem einzelnen Stichwort zugeordnet werden.
  
Multipurpose Internet Mail Extensions (MIME)-Autoren sollten jeder untergeordneten Wert dieser Eigenschaft zu einem separaten Stichwort in das Feld Schlüsselwörter Kopf durch ein Komma (U + 002 C) und Leerzeichen (U + 0020) trennen kopieren jedes Schlüsselwort. MIME-Writer können diese Eigenschaft nicht kopiert werden soll, um einen Konflikt zwischen verschiedenen Sätze von Kategorien in unterschiedlichen Organisationen zu vermeiden dem Feld Stichwörter Kopfzeile löschen.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Set Eigenschaftendefinition und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
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

