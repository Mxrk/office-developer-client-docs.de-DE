---
title: Kanonische PidTagRtfCompressed-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRtfCompressed
api_type:
- COM
ms.assetid: fd0ccb88-55ce-4d7c-9573-6e5d6239b6a8
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: c93d850551e766e97292d5417c3be5577f557af0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795005"
---
# <a name="pidtagrtfcompressed-canonical-property"></a>Kanonische PidTagRtfCompressed-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Die Rich Text Format (RTF) Version des Texts Nachricht in der Regel in komprimierter Form enthält. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_RTF_COMPRESSED  <br/> |
|Bezeichner:  <br/> |0 x 1009  <br/> |
|Datentyp:  <br/> |PT_BINARY  <br/> |
|Bereich:  <br/> |E-Mail  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft enthält den gleichen Nachrichtentext als **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))-Eigenschaft, aber in RTF. 
  
Nachrichtentext in RTF wird normalerweise in komprimierter Form gespeichert. Einige Systeme komprimieren formatierten Text jedoch nicht. Um diese zu unterstützen, stellt MAPI den DwMagicUncompressedRTF Wert für eine Kopfzeile Stream zum Identifizieren der nicht komprimierten RTF und das Flag **STORE_UNCOMPRESSED_RTF** in **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) für die Nachricht Speichern Sie, um darauf hinzuweisen, dass es nicht komprimierten RTF gespeichert werden kann. 
  
Um den Inhalt dieser Eigenschaft abzurufen, **OpenProperty**und anschließend rufen Sie [WrapCompressedRTFStream](wrapcompressedrtfstream.md) mit dem **MAPI_READ** -Flag auf. Um diese Eigenschaft zu schreiben, öffnen Sie es mit den Flags **MAPI_MODIFY** und **MAPI_CREATE ist** . Dadurch wird sichergestellt, dass die neuen Daten vollständig alle alten Daten ersetzen und schreibt die mit der Mindestanzahl von Store-Updates durchgeführt werden. 
  
Nachrichtenspeicher, die RTF unterstützen ignorieren Änderungen an Leerzeichen im Nachrichtentext. Wenn **PR_BODY** zum ersten Mal gespeichert wird, wird der Nachrichtenspeicher auch generiert und speichert diese Eigenschaft. Wenn später die [IMAPIProp::SaveChanges](imapiprop-savechanges.md) -Methode aufgerufen wird und **PR_BODY** geändert wurde, ruft der Nachrichtenspeicher die [RTFSync](rtfsync.md) -Funktion, um die Synchronisierung mit der RTF-Version sicherzustellen. Wenn nur Leerzeichen geändert wurde, werden die Eigenschaften left unverändert. Dadurch bleibt erhalten alle nicht trivialen RTF Formatierung beim Clients RTF nicht unterstützen die Nachricht durchläuft und messaging-Systeme. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Nachrichten und Anlagen Objekte behandelt.
    
[[MS-OXRTFCP]](http://msdn.microsoft.com/library/65dfe2df-1b69-43fc-8ebd-21819a7463fb%28Office.15%29.aspx)
  
> Codiert und decodiert einen komprimierten Datenstrom im RTF-Nachrichtentexte.
    
[[MS-OXRTFEX]](http://msdn.microsoft.com/library/411d0d58-49f7-496c-b8c3-5859b045f6cf%28Office.15%29.aspx)
  
> Kapselt zusätzliche Content-Formate (wie HTML) in die Body-Eigenschaft von RTF-Nachrichten und Anlagen.
    
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

