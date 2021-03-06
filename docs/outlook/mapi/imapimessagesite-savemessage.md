---
title: IMAPIMessageSiteSaveMessage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIMessageSite.SaveMessage
api_type:
- COM
ms.assetid: 94c44952-d297-4705-9778-90373dfa5ad6
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: ec85f7bdfc9d2d275bdb5ffe7ba0113ad4a35c3b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792228"
---
# <a name="imapimessagesitesavemessage"></a>IMAPIMessageSite::SaveMessage

  
  
**Betrifft**: Outlook 
  
Anforderungen, die die aktuelle Nachricht gespeichert werden soll.
  
```cpp
HRESULT SaveMessage( void );
```

## <a name="parameters"></a>Parameter

None.
  
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Aufruf erfolgreich ausgef�hrt und der erwartete Wert oder Werte zur�ckgegeben hat. 
    
## <a name="remarks"></a>Hinweise

Formulare rufen Sie die **IMAPIMessageSite::SaveMessage** -Methode, um anzufordern, dass eine Nachricht gespeichert werden. 
  
Eine Liste der Schnittstellen im Zusammenhang mit der Formular-Servern finden Sie unter [MAPI-Formulars Schnittstellen](mapi-form-interfaces.md).
  
## <a name="mfcmapi-reference"></a>MFCMAPI (engl.) (engl.)

Beispielcode MFCMAPI (engl.) finden Sie in der folgenden Tabelle.
  
|**Datei**|**Funktion**|**Comment**|
|:-----|:-----|:-----|
|MyMAPIFormViewer.cpp  <br/> |CMyMAPIFormViewer::SaveMessage  <br/> |MFCMAPI (engl.) verwendet die **IMAPIMessageSite::SaveMessage** -Methode, um die Nachricht zu speichern.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md)


[MFCMAPI (engl.) als ein Codebeispiel](mfcmapi-as-a-code-sample.md)
  
[MAPI-Formulars Schnittstellen](mapi-form-interfaces.md)

