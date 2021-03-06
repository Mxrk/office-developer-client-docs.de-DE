---
title: IMsgStoreGetReceiveFolderTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetReceiveFolderTable
api_type:
- COM
ms.assetid: d115ab58-07d2-4b49-8e08-2881c2924102
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 8146b5c2b9c9fb5429a9c1d46bca687c32bcf3dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792641"
---
# <a name="imsgstoregetreceivefoldertable"></a>IMsgStore::GetReceiveFolderTable

  
  
**Betrifft**: Outlook 
  
Bietet Zugriff auf die empfangen Ordnertabelle Tabelle Informationen zu allen der Ordner für den Nachrichtenspeicher empfangen enthält.
  
```cpp
HRESULT GetReceiveFolderTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable );
```

## <a name="parameters"></a>Parameter

 _ulFlags_
  
> [in] Eine Bitmaske der Werte, dass Steuerelemente Access-Tabelle. Die folgenden Kennzeichen können festgelegt werden:
    
MAPI_DEFERRED_ERRORS 
  
> Ermöglicht **GetReceiveFolderTable** erfolgreich, möglicherweise beendet, bevor die Tabelle mit dem Anrufer vollständig verfügbar ist. Wenn die Tabelle nicht vollständig verfügbar ist, kann die nachfolgenden Tabelle Anrufen ein Fehler ausgelöst. 
    
PARAMETER MAPI_UNICODE 
  
> Die zurückgegebenen Zeichenfolgen sind im Unicode-Format. Wenn die Option MAPI_UNICODE nicht festgelegt ist, sind die Zeichenfolgen in ANSI-Format.
    
 _lppTable_
  
> [out] Ein Zeiger auf einen Zeiger auf den Ordner-empfangen-Tabelle.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Die Ordner-Tabelle empfangen wurde erfolgreich zurückgegeben.
    
## <a name="remarks"></a>Hinweise

Die **IMsgStore::GetReceiveFolderTable** -Methode ermöglicht den Zugriff auf eine Tabelle, die anzeigt, dass die Einstellungen für alle des Nachrichtenspeicher Ordner erhalten. 
  
## <a name="notes-to-implementers"></a>Hinweise für Implementierer

Eine Liste der erforderlichen Spalten in einem Ordner empfangen finden Sie unter [Ordner Tabellen erhalten](receive-folder-tables.md). 
  
Implementieren der Ordner Tabellen Suchkriterien in Eigenschaft die Einstellung für die Eigenschaft **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) Unterstützung erhalten. Diese einfache ermöglicht den Zugriff auf bestimmte empfangen Ordner.
  
## <a name="notes-to-callers"></a>Hinweise für Aufrufer

Festlegen der Option MAPI_UNICODE im Parameter _UlFlags_ wirkt sich auf das Format der von den Methoden [IMAPITable::QueryColumns](imapitable-querycolumns.md) und [IMAPITable::QueryRows](imapitable-queryrows.md) zurückgegebenen Spalten aus. Dieses Kennzeichen steuert auch die Eigenschaftentypen in der Sortierreihenfolge, die von der [IMAPITable::QuerySortOrder](imapitable-querysortorder.md) -Methode zurückgegeben. 
  
## <a name="mfcmapi-reference"></a>MFCMAPI (engl.) (engl.)

Beispielcode MFCMAPI (engl.) finden Sie in der folgenden Tabelle.
  
|**Datei**|**Funktion**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnDisplayReceiveFolderTable  <br/> |MFCMAPI (engl.) verwendet die **IMsgStore::GetReceiveFolderTable** -Methode zum Abrufen der empfangen Ordnertabelle angezeigt.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[IMAPITable::QueryColumns](imapitable-querycolumns.md)
  
[IMAPITable::QueryRows](imapitable-queryrows.md)
  
[IMAPITable::QuerySortOrder](imapitable-querysortorder.md)
  
[IMAPITable::SetColumns](imapitable-setcolumns.md)
  
[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI (engl.) als ein Codebeispiel](mfcmapi-as-a-code-sample.md)

