---
title: Kanonische PidTagIpmAppointmentEntryId-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmAppointmentEntryId
api_type:
- HeaderDef
ms.assetid: a6e8c8fb-b76a-4a73-b112-6399e4d94233
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 231b905c4288379384530c7b35200eefb63479d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794528"
---
# <a name="pidtagipmappointmententryid-canonical-property"></a>Kanonische PidTagIpmAppointmentEntryId-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Die **EntryID** des Ordners Outlook-Kalender enthält. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_IPM_APPOINTMENT_ENTRYID  <br/> |
|Bezeichner:  <br/> |0x36D0  <br/> |
|Datentyp:  <br/> |PT_BINARY  <br/> |
|Bereich:  <br/> |Ordner  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft wird im Ordner Posteingang und im Stammordner des Nachrichtenspeichers gespeichert. Zugriff auf die Eigenschaft auf eine bestimmte Nachricht Store die folgenden Schritte aus. 
  
1. Suchen Sie zunächst nach der Eigenschaft im Ordner Posteingang. Verwenden Sie [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) , um einen Verweis auf die **Eintrags-ID** für den Ordner Posteingang abzurufen. 
    
2. Wenn **IMsgStore::GetReceiveFolder** erfolgreich ist, verwenden Sie den Verweis auf die **EntryID** des Posteingang und [IMsgStore::OpenEntry](imsgstore-openentry.md) zum Öffnen des Posteingangs, und rufen Sie einen Verweis auf ein Objekt **IMAPIFolder** . 
    
3. Wenn **IMsgStore::OpenEntry** erfolgreich ist, müssen verwenden Sie den zurückgegebenen Verweis auf das **IMAPIFolder** -Objekt und [IMAPIProp::GetProps](imapiprop-getprops.md) dann, um die gewünschte Eigenschaft abzurufen. 
    
4. Wenn Schritt 1, 2 oder 3 fehlschlägt, suchen Sie nach der-Eigenschaft im Stammordner gespeichert. Verwenden Sie hierzu **IMsgStore::OpenEntry**, Angeben von NULL für die **LpEntryID**, um den Stammordner des Nachrichtenspeichers öffnen, und rufen Sie einen Verweis auf das **IMAPIFolder** -Objekt. 
    
5. Wenn Stammordner öffnen erfolgreich ist, müssen verwenden Sie den zurückgegebenen Verweis auf das **IMAPIFolder** -Objekt und **IMAPIProp::GetProps** dann, um die gewünschte Eigenschaft abzurufen. 
    
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen für das Erstellen und Ordner mit Sonderfunktion in einem Postfach suchen.
    
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

