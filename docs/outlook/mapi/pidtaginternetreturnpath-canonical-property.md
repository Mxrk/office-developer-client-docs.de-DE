---
title: Kanonische PidTagInternetReturnPath-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInternetReturnPath
api_type:
- HeaderDef
ms.assetid: 4530dbcf-9436-4f29-b79e-1bb0f791f60b
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: aa8a683c0033682aa46944c5cc78503dc1a7d729
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794502"
---
# <a name="pidtaginternetreturnpath-canonical-property"></a>Kanonische PidTagInternetReturnPath-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält den Wert der Rückgabe-Path-Header ein Feld einer Nachricht Multipurpose Internet Mail Extensions (MIME). Die e-Mail-Adresse des Absenders der Nachricht.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_INTERNET_RETURN_PATH, PR_INTERNET_RETURN_PATH_A, PR_INTERNET_RETURN_PATH_W  <br/> |
|Bezeichner:  <br/> |0x1046  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |MIME  <br/> |
   
## <a name="remarks"></a>Hinweise

Um den Wert dieser Eigenschaft abzurufen, zunächst mit dem [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) um das Eigenschafts-Tag zu erhalten, und geben Sie in [IMAPIProp::GetProps](imapiprop-getprops.md) zum Abrufen des Werts dieser Eigenschaftentag. Beim Aufruf von [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), geben Sie die folgenden Werte für die [MAPINAMEID](mapinameid.md) -Struktur an, das Eingabeparameter _LppPropNames_auf zeigt:
  
|||
|:-----|:-----|
|x LpGuid:  <br/> |PS_INTERNET_HEADERS  <br/> |
|UlKind:  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName:  <br/> |L "Return-Pfad"  <br/> |
   
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)
  
> Konvertiert zwischen IETF RFC2445, RFC2446, RFC2447, und Termine und meeting-Objekte.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
Mapitags.h
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[MAPI-Konstanten](mapi-constants.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

