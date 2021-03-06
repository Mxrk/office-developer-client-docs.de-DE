---
title: Überwachen von Änderungen am Status von Verbindung mit einer offline-Status-add-in
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: c482ddce-f2b6-222b-aa30-824b1c6f3b14
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 9f7f3bc0e305fb5aa7d6ae1e1909b573b3376ef8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793266"
---
# <a name="monitoring-connection-state-changes-using-an-offline-state-add-in"></a>Überwachen von Änderungen am Status von Verbindung mit einer offline-Status-add-in

**Betrifft**: Outlook 
  
Bevor Sie zum Überwachen von Änderungen am Status der Verbindung eine offline-Status-Add-in verwenden können, müssen Sie die Funktionen zum Einrichten und initialisieren Sie das Add-in implementieren. Weitere Informationen finden Sie unter [Einstellung Up eine Offline-Status-Add-in](setting-up-an-offline-state-add-in.md).
  
Nach dem Einrichten des offline-Status-add-Ins, müssen Sie die **[HrOpenOfflineObj](hropenofflineobj.md)** -Funktion verwenden, um eine offline-Objekt abzurufen. Verwenden diese offline-Objekts, können Sie Ihren Monitor Zustand initialisieren und dann abrufen und Festlegen des aktuellen Zustands. 
  
In diesem Thema werden die folgenden Überwachungsfunktionen Status mithilfe der Offline-Status Beispiel-Add-in Codebeispielen veranschaulicht. Das Offline-Status Beispiel-Add-in ist ein COM-add-in, die ein Menü **Status als offline anzeigen** zu Outlook hinzugefügt und State-API verwendet. Über das Menü **Offline-Status** können Sie aktivieren oder Deaktivieren der Status der Überwachung, überprüfen Sie den aktuellen Status und ändern den aktuellen Status. Weitere Informationen zum Herunterladen und Installieren der Offline-Status Beispiel-Add-Ins finden Sie unter [Installieren der Offline-Status Beispiel-Add-Ins](installing-the-sample-offline-state-add-in.md). Weitere Informationen zur Status-API finden Sie unter [Über die Offline Zustand-API](about-the-offline-state-api.md).
  
Wenn das Add-in offline-Status getrennt ist, müssen Sie implementieren Funktionen zum ordnungsgemäß beendet und bereinigen Sie das Add-in. Weitere Informationen finden Sie unter [Trennen eines Status Offline-Add-Ins](disconnecting-an-offline-state-add-in.md).
  
## <a name="open-offline-object-routine"></a>Open Offline-Objekt routine

Für den Client benachrichtigt werden, wenn Verbindung Status geändert wird müssen Sie die Funktion **[HrOpenOfflineObj](hropenofflineobj.md)** aufrufen. Diese Funktion öffnet ein offline-Objekt, das **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)** unterstützt. Die **HrOpenOfflineObj** -Funktion ist in der Headerdatei ConnectionState.h definiert. 
  
> [!NOTE]
> Die **HrOpenOfflineObj** -Funktion wird in der Headerdatei ImportProcs.h wie folgt deklariert: `extern HROPENOFFLINEOBJ* pfnHrOpenOfflineObj;`. 
  
### <a name="hropenofflineobj-example"></a>HrOpenOfflineObj-Beispiel

```cpp
typedef HRESULT (STDMETHODCALLTYPE HROPENOFFLINEOBJ)( 
    ULONG ulFlags, 
    LPCWSTR pwszProfileName, 
    const GUID* pGUID, 
    const GUID* pInstance, 
    IMAPIOfflineMgr** ppOffline 
);
```

## <a name="initialize-monitor-routine"></a>Initialisieren der Monitor routine

Die `InitMonitor` Funktion ruft die **HrOpenOfflineObj** -Funktion. Die `InitMonitor` Funktion **CMyOfflineNotify** aufruft, damit Outlook Rückruf Benachrichtigungen an den Client senden kann, und den Rückruf über die Variable **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** registriert `AdviseInfo`.
  
### <a name="initmonitor-example"></a>InitMonitor()-Beispiel

```cpp
void InitMonitor(LPCWSTR szProfile) 
{ 
    if (!szProfile) return; 
    Log(true,_T("Initializing Outlook Offline State Monitor\n")); 
    HRESULT hRes = S_OK; 
 
    if (g_lpOfflineMgr) 
    { 
        Log(true,_T("Already initialized\n")); 
        return; 
    } 
     
    if (pfnHrOpenOfflineObj) 
    { 
        if (g_lpOfflineMgr) DeInitMonitor(); 
        Log(true,_T("Calling HrOpenOfflineObj for \"%ws\"\n"),szProfile); 
        hRes = pfnHrOpenOfflineObj( 
            NULL, 
            szProfile, 
            &GUID_GlobalState, 
            NULL, 
            &g_lpOfflineMgr); 
        if (FAILED(hRes))  
        { 
            Log(true,_T("HrOpenOfflineObj failed: 0x%08X\n"),hRes); 
        } 
        if (g_lpOfflineMgr) 
        { 
            IMAPIOffline* lpOffline = NULL; 
            hRes = g_lpOfflineMgr->QueryInterface(IID_IMAPIOffline,(LPVOID*)&lpOffline); 
             
            if (lpOffline) 
            { 
                ULONG ulCap = NULL; 
                hRes = lpOffline->GetCapabilities(&ulCap); 
                 
                if (ulCap & MAPIOFFLINE_CAPABILITY_OFFLINE) Log(true,_T("MAPIOFFLINE_CAPABILITY_OFFLINE supported\n")); 
                if (ulCap & MAPIOFFLINE_CAPABILITY_ONLINE) Log(true,_T("MAPIOFFLINE_CAPABILITY_ONLINE supported\n")); 
                 
                if (ulCap & (MAPIOFFLINE_CAPABILITY_OFFLINE | MAPIOFFLINE_CAPABILITY_ONLINE)) 
                { 
                    CMyOfflineNotify* lpImplNotify = new CMyOfflineNotify(); 
                     
                    if (lpImplNotify) 
                    { 
                        MAPIOFFLINE_ADVISEINFO AdviseInfo = {0}; 
                        AdviseInfo.ulSize = sizeof(MAPIOFFLINE_ADVISEINFO); 
                        AdviseInfo.ulClientToken = 0;// something you want to get handed back when you get the notification 
                        AdviseInfo.CallbackType = MAPIOFFLINE_CALLBACK_TYPE_NOTIFY; 
                        AdviseInfo.pCallback = lpImplNotify; 
                        AdviseInfo.ulAdviseTypes = MAPIOFFLINE_ADVISE_TYPE_STATECHANGE; 
                        AdviseInfo.ulStateMask = MAPIOFFLINE_STATE_ALL; 
                         
                        hRes = g_lpOfflineMgr->Advise(MAPIOFFLINE_ADVISE_DEFAULT, &AdviseInfo, &g_ulAdviseToken); 
                        Log(true,"ulAdviseToken = 0x%08X\n",g_ulAdviseToken); 
                    } 
                } 
                lpOffline->Release(); 
            }                 
        } 
    } 
}
```

## <a name="get-current-state-routine"></a>Abrufen aktueller Zustand routine

Die `GetCurrentState` Funktion ruft die **HrOpenOfflineObj** -Funktion, und klicken Sie dann das offline-Objekt verwendet, um den aktuellen Verbindungsstatus abzurufen. Der aktuelle Status wird zurückgegeben, der `ulCurState` Variable, die in verwendet wird die `CButtonEventHandler::Click` Funktion, um den aktuellen Status für den Benutzer anzuzeigen. 
  
### <a name="getcurrentstate-example"></a>GetCurrentState()-Beispiel

```cpp
ULONG (LPCWSTR szProfile) 
{ 
    if (!szProfile) return 0; 
    Log(true,_T("Getting Current Offline State\n")); 
    HRESULT hRes = S_OK; 
    ULONG ulCurState = NULL; 
 
    if (pfnHrOpenOfflineObj) 
    { 
        if (g_lpOfflineMgr) DeInitMonitor(); 
        Log(true,_T("Calling HrOpenOfflineObj for \"%ws\"\n"),szProfile); 
        hRes = pfnHrOpenOfflineObj( 
            NULL, 
            szProfile, 
            &GUID_GlobalState, 
            NULL, 
            &g_lpOfflineMgr); 
        if (FAILED(hRes))  
        { 
            Log(true,_T("HrOpenOfflineObj failed: 0x%08X\n"),hRes); 
        } 
        if (g_lpOfflineMgr) 
        { 
            IMAPIOffline* lpOffline = NULL; 
            hRes = g_lpOfflineMgr->QueryInterface(IID_IMAPIOffline,(LPVOID*)&lpOffline); 
             
            if (lpOffline) 
            { 
                hRes = lpOffline->GetCurrentState(&ulCurState); 
                Log(true,_T("GetCurrentState returned 0x%08X\n"),hRes); 
 
                switch(ulCurState) 
                { 
                case MAPIOFFLINE_STATE_ONLINE: 
                    Log(true,_T("Current state is MAPIOFFLINE_STATE_ONLINE\n")); 
                    break; 
                case MAPIOFFLINE_STATE_OFFLINE: 
                    Log(true,_T("Current state is MAPIOFFLINE_STATE_OFFLINE\n")); 
                    break; 
                default: 
                    Log(true,_T("Current state is 0x%0X\n"),ulCurState); 
                } 
                lpOffline->Release(); 
            } 
        } 
    } 
    return ulCurState; 
}
```

## <a name="set-current-state-routine"></a>Set Aktueller Zustand routine

Die `SetCurrentState` Funktion ruft die **HrOpenOfflineObj** -Funktion, und klicken Sie dann das offline-Objekt verwendet, um den aktuellen Verbindungsstatus festzulegen. Die `CButtonEventHandler::Click` Funktionsaufrufe der `SetCurrentState` -Funktion und den neuen Zustand übergeben wird über die `ulState` Variable. 
  
### <a name="setcurrentstate-example"></a>SetCurrentState()-Beispiel

```cpp
HRESULT SetCurrentState(LPCWSTR szProfile, ULONG ulFlags, ULONG ulState) 
{ 
    if (!szProfile) return 0; 
    Log(true,_T("Setting Current Offline State\n")); 
    HRESULT hRes = S_OK; 
 
    if (pfnHrOpenOfflineObj) 
    { 
        if (g_lpOfflineMgr) DeInitMonitor(); 
        Log(true,_T("Calling HrOpenOfflineObj for \"%ws\"\n"),szProfile); 
        hRes = pfnHrOpenOfflineObj( 
            NULL, 
            szProfile, 
            &GUID_GlobalState, 
            NULL, 
            &g_lpOfflineMgr); 
        if (FAILED(hRes))  
        { 
            Log(true,_T("HrOpenOfflineObj failed: 0x%08X\n"),hRes); 
        } 
        if (g_lpOfflineMgr) 
        { 
            IMAPIOffline* lpOffline = NULL; 
            hRes = g_lpOfflineMgr->QueryInterface(IID_IMAPIOffline,(LPVOID*)&lpOffline); 
             
            if (lpOffline) 
            { 
                switch(ulFlags) 
                { 
                case MAPIOFFLINE_FLAG_BLOCK: 
                    Log(true,_T("Flag used: MAPIOFFLINE_FLAG_BLOCK\n")); 
                    break; 
                case MAPIOFFLINE_FLAG_DEFAULT: 
                    Log(true,_T("Flag used: MAPIOFFLINE_FLAG_DEFAULT\n")); 
                    break; 
                default: 
                    Log(true,_T("Flag used: 0x%0X\n"),ulFlags); 
                } 
                switch(ulState) 
                { 
                case MAPIOFFLINE_STATE_ONLINE: 
                    Log(true,_T("New state will be MAPIOFFLINE_STATE_ONLINE\n")); 
                    break; 
                case MAPIOFFLINE_STATE_OFFLINE: 
                    Log(true,_T("New state will be MAPIOFFLINE_STATE_OFFLINE\n")); 
                    break; 
                default: 
                    Log(true,_T("New state will be 0x%0X\n"),ulState); 
                } 
                hRes = lpOffline->SetCurrentState(ulFlags, MAPIOFFLINE_STATE_OFFLINE_MASK,ulState,NULL); 
                Log(true,_T("SetCurrentState returned 0x%08X\n"),hRes); 
                 
                lpOffline->Release(); 
            } 
        } 
    } 
    return hRes; 
}
```

## <a name="notification-routine"></a>Benachrichtigungsroutine

Die Funktion **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** wird von Outlook zum Senden von Benachrichtigungen bei Änderungen in den Verbindungsstatus an einen Client verwendet. 
  
### <a name="cmyofflinenotifynotify-example"></a>CMyOfflineNotify::Notify()-Beispiel

```cpp
void CMyOfflineNotify::Notify(const MAPIOFFLINE_NOTIFY *pNotifyInfo) 
{ 
    Log(true,_T("CMyOfflineNotify::Notify\n")); 
    if    (pNotifyInfo == NULL) 
    {     
        Log(true,_T("pNotifyInfo is NULL\n")); 
    } 
    else 
    { 
        Log(true,_T("pNotifyInfo->ulSize == 0x%0X\n"),pNotifyInfo->ulSize); 
        switch(pNotifyInfo->NotifyType) 
        { 
            case    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE: 
                Log(true,_T("pNotifyInfo->NotifyType == MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE\n")); 
                break; 
            case    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START: 
                Log(true,_T("pNotifyInfo->NotifyType == MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_START\n")); 
                break; 
            case    MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE: 
                Log(true,_T("pNotifyInfo->NotifyType == MAPIOFFLINE_NOTIFY_TYPE_STATECHANGE_DONE\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->NotifyType == 0x%08X\n"),pNotifyInfo->NotifyType); 
        } 
        Log(true,_T("pNotifyInfo->ulClientToken == 0x%0X\n"),pNotifyInfo->ulClientToken); 
        switch(pNotifyInfo->Info.StateChange.ulMask) 
        { 
            case    MAPIOFFLINE_STATE_OFFLINE_MASK: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulMask == MAPIOFFLINE_STATE_OFFLINE_MASK\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulMask == 0x%0X\n"),pNotifyInfo->Info.StateChange.ulMask); 
        } 
        switch(pNotifyInfo->Info.StateChange.ulStateOld) 
        { 
            case    MAPIOFFLINE_STATE_ONLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateOld == MAPIOFFLINE_STATE_ONLINE\n")); 
                break; 
            case    MAPIOFFLINE_STATE_OFFLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateOld == MAPIOFFLINE_STATE_OFFLINE\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateOld == 0x%0X\n"),pNotifyInfo->Info.StateChange.ulStateOld); 
        } 
        switch(pNotifyInfo->Info.StateChange.ulStateNew) 
        { 
            case    MAPIOFFLINE_STATE_ONLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateNew == MAPIOFFLINE_STATE_ONLINE\n")); 
                break; 
            case    MAPIOFFLINE_STATE_OFFLINE: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateNew == MAPIOFFLINE_STATE_OFFLINE\n")); 
                break; 
            default: 
                Log(true,_T("pNotifyInfo->Info.StateChange.ulStateNew == 0x%0X\n"),pNotifyInfo->Info.StateChange.ulStateNew); 
        } 
    } 
    return; 
}
```

## <a name="see-also"></a>Siehe auch

- [Über die Offline State-API](about-the-offline-state-api.md)
- [Installieren das Beispiel Offline State-Add-in](installing-the-sample-offline-state-add-in.md)
- [Zum Beispiel Offline State-Add-in](about-the-sample-offline-state-add-in.md)
- [Einrichten von einem Offline State Add-in](setting-up-an-offline-state-add-in.md)
- [Trennen der Verbindung ein Offline State-Add-in](disconnecting-an-offline-state-add-in.md)

