---
title: Kanonische PidTagContainerClass-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerClass
api_type:
- HeaderDef
ms.assetid: db249e9e-f1f0-4b95-8cd9-daa7c53ddb32
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 9d40c21cde6bf3a6e8e37dda80dd6f900f233a0e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794213"
---
# <a name="pidtagcontainerclass-canonical-property"></a>Kanonische PidTagContainerClass-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält eine Textzeichenfolge, die den Typ eines Ordners. Obwohl diese Eigenschaft im Allgemeinen ignoriert wird, erwarten Versionen von Microsoft® Exchange Server vor Exchange Server 2003-Postfach-Manager diese Eigenschaft vorhanden sein.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_CONTAINER_CLASS, PR_CONTAINER_CLASS_A, PR_CONTAINER_CLASS_W  <br/> |
|Bezeichner:  <br/> |0x3613  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |Container  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften werden normalerweise nicht vom Exchange-Server verwendet. Allerdings fügt Microsoft Office Outlook® sie an den Postfachordner. Darüber hinaus-Versionen von Exchange Server vor Exchange Server 2003-Postfach-Manager möglicherweise nicht ordnungsgemäß Ordner verarbeitet, die nicht über diese Eigenschaften verfügen.
  
Diese Eigenschaften können die Zeichenfolgenwerte in der folgenden Tabelle zugewiesen werden.
  
|**Wert**|**Inhalt des Ordners**|
|:-----|:-----|
|IPF. Termin  <br/> |Termine  <br/> |
|IPF. Kontakt  <br/> |Kontakte  <br/> |
|IPF. Journal  <br/> |Outlook-Journaleinträge  <br/> |
|IPF. Hinweis  <br/> |E-Mail-Nachrichten und Notizen  <br/> |
|IPF. StickyNote  <br/> |Outlook-Kurznotizen  <br/> |
|IPF. Aufgabe  <br/> |Outlook-Aufgaben  <br/> |
   
Für Ordner, die e-Mail-Nachrichten enthalten, sollten diese Eigenschaften auf IPF festgelegt werden. Beachten Sie.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen für das Erstellen und Ordner mit Sonderfunktion in einem Postfach suchen.
    
[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für den Termin, einer Besprechungsanfrage und Antwortnachrichten.
    
[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für Kontakt- und Objekte in der persönlichen Verteilerliste Liste zulässig sind.
    
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

