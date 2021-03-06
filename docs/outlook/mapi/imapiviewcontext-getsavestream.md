---
title: IMAPIViewContextGetSaveStream
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewContext.GetSaveStream
api_type:
- COM
ms.assetid: 8316bfa1-3077-401f-aa1e-e9492aca12a8
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 7981dc8550485aa22859c4a8dc25541bedf1217c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792502"
---
# <a name="imapiviewcontextgetsavestream"></a>IMAPIViewContext::GetSaveStream

  
  
**Betrifft**: Outlook 
  
Ruft einen Datenstrom zum Speichern der aktuellen Nachricht verwendet werden soll.
  
```cpp
HRESULT GetSaveStream(
ULONG FAR * pulFlags,
ULONG FAR * pulFormat,
LPSTREAM FAR * ppstm
);
```

## <a name="parameters"></a>Parameter

 _pulFlags_
  
> [out] Zeiger auf eine Bitmaske aus Flags, die steuert, wie der Nachrichtentext gespeichert werden soll. Das folgende Flag kann festgelegt werden:
    
PARAMETER MAPI_UNICODE 
  
> Der Meldungstext wird im Unicode-Format gespeichert. Wenn die Option MAPI_UNICODE nicht festgelegt ist, wird der Text im ANSI-Format gespeichert.
    
 _pulFormat_
  
> [out] Zeiger auf eine Bitmaske aus Flags, die das Format des gespeicherten Texts steuert. Die folgenden Kennzeichen können festgelegt werden:
    
SAVE_FORMAT_RICHTEXT 
  
> Der Nachrichtentext wird als formatierter Text im Rich Text Format (RTF) gespeichert werden soll. 
    
SAVE_FORMAT_TEXT 
  
> Der Nachrichtentext wird als nur-Text gespeichert werden soll. 
    
 _ppstm_
  
> [out] Zeiger auf einen Zeiger in das Stream-Objekt, das die gespeicherte Nachricht enthält.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Stream wurde erfolgreich abgerufen.
    
## <a name="remarks"></a>Hinweise

Formularobjekte aufrufen, die **IMAPIViewContext::GetSaveStream** -Methode, um einen Datenstrom ein Objekt abzurufen, die zur Unterstützung der der Handhabung des Verbs speichern unter im Formular-Viewer die **IStream** -Schnittstelle implementiert wird. Die [IMAPIForm::DoVerb](imapiform-doverb.md) -Methode, die in dem Formular Server implementiert und von der Formular-Viewer zum Aufrufen eines Verbs aufgerufen, sollten keine zurückgegeben, bis die Nachricht vollständig in die entsprechenden Textformat konvertiert und in den entsprechenden Stream platziert. 
  
## <a name="notes-to-callers"></a>Hinweise für Aufrufer

Nicht in das Stream-Objekt, auf die _Ppstm_ vor dem Aufruf von **GetSaveStream**schreiben. Wenn **GetSaveStream** zurückgegeben wird, sollten Sie die Position des Mauszeigers Seek nicht zurücksetzen. Dieser Zeiger muss am Ende des Texts gespeicherte Nachricht bleiben. 
  
## <a name="see-also"></a>Siehe auch



[IMAPIViewContext: IUnknown](imapiviewcontextiunknown.md)

