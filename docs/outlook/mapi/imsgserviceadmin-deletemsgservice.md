---
title: IMsgServiceAdminDeleteMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.DeleteMsgService
api_type:
- COM
ms.assetid: 3a6b34eb-9d46-488f-8d02-91b27c35de67
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 0a3021ed386aa00777694452a755693fc4078093
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792590"
---
# <a name="imsgserviceadmindeletemsgservice"></a>IMsgServiceAdmin::DeleteMsgService

  
  
**Betrifft**: Outlook 
  
Löscht eine Message Service aus einem Profil.
  
```cpp
HRESULT DeleteMsgService(
  LPMAPIUID lpuid
);
```

## <a name="parameters"></a>Parameter

 _lpuid_
  
> [in] Ein Zeiger auf die [MAPIUID](mapiuid.md) -Struktur, die den eindeutigen Bezeichner für den zu löschenden Nachrichtendienst enthält. 
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Nachrichtendienst wurde gelöscht.
    
MAPI_E_NOT_FOUND 
  
> Die auf den _Lpuid_ **MAPIUID** stimmt nicht mit einer vorhandenen Messagingdiensts überein. 
    
## <a name="remarks"></a>Hinweise

Die **IMsgServiceAdmin::DeleteMsgService** -Methode löscht eine Message Service aus einem Profil. **DeleteMsgService** entfernt alle Profil Abschnitte im Zusammenhang mit den Dienst. 
  
 **DeleteMsgService** führt die folgenden Schritte aus, um den Dienst zu löschen: 
  
1. Ruft die Messagingdiensts Eintrag Point-Funktion mit dem _UlContext_ -Parameter auf MSG_SERVICE_DELETE festgelegt werden, bevor die Abschnitte Profil entfernt werden. Dadurch wird den Dienst dienstspezifische Aufgaben ausgeführt. 
    
2. Löscht den Dienst an.
    
3. Löscht die Messagingdiensts Profilabschnitt.
    
Die Messagingdiensts Eintrag Point-Funktion wird nicht erneut aufgerufen, nachdem der Dienst gelöscht wurde.
  
## <a name="notes-to-callers"></a>Hinweise für Aufrufer

Zum Abrufen der **MAPIUID** -Struktur für den Dienst zu löschen, Abrufen die Spalte **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) aus der Nachrichtendienst Zeile in der Tabelle der Dienste. Weitere Informationen finden Sie unter dem Verfahren in der [IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md) -Methode. 
  
## <a name="mfcmapi-reference"></a>MFCMAPI (engl.) (engl.)

Beispielcode MFCMAPI (engl.) finden Sie in der folgenden Tabelle.
  
|**Datei**|**Funktion**|**Comment**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg::OnDeleteSelectedItem  <br/> |MFCMAPI (engl.) verwendet die **IMsgServiceAdmin::DeleteMsgService** -Methode, um die ausgewählte dienstanwendung zu löschen.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin: IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI (engl.) als ein Codebeispiel](mfcmapi-as-a-code-sample.md)

