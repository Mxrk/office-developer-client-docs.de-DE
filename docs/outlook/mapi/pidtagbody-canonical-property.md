---
title: Kanonische PidTagBody-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBody
api_type:
- HeaderDef
ms.assetid: 47c0d0fe-4d57-4b81-bdb5-336de85c194c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 23d943d5576f5e9d7694b03c90dea79a878dee64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794134"
---
# <a name="pidtagbody-canonical-property"></a>Kanonische PidTagBody-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält den Nachrichtentext.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_BODY, PR_BODY_A, PR_BODY_W  <br/> |
|Bezeichner:  <br/> |0 x 1000  <br/> |
|Datentyp:  <br/> |PT_UNICODE PT_STRING8  <br/> |
|Bereich:  <br/> |Allgemeine messaging  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften werden in der Regel nur in einer zwischen Personen Nachricht (IPM) verwendet. 
  
Nachrichtenspeicher, die Rich Text Format (RTF) unterstützen ignorieren Änderungen an Leerzeichen im Nachrichtentext. Wenn **PR_BODY** zum ersten Mal gespeichert wird, wird der Nachrichtenspeicher auch generiert und speichert die RTF-Version des Texts Message-Eigenschaft **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)). Wenn später die [IMAPIProp::SaveChanges](imapiprop-savechanges.md) -Methode aufgerufen wird und **PR_BODY** geändert wurde, ruft der Nachrichtenspeicher die [RTFSync](rtfsync.md) -Funktion, um die Synchronisierung mit der RTF-Version sicherzustellen. Wenn nur Leerzeichen geändert wurde, werden die Eigenschaften left unverändert. Dadurch bleibt erhalten alle nicht trivialen RTF Formatierung beim Clients RTF nicht unterstützen die Nachricht durchläuft und messaging-Systeme. 
  
Der Wert für diese Eigenschaft muss in der Codepage des Betriebssystems ausgedrückt werden, die MAPI ausgeführt wird. 
  
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



[Kanonische PidTagRtfInSync-Eigenschaft](pidtagrtfinsync-canonical-property.md)


[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

