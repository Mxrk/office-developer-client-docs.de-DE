---
title: HrOpenOfflineObj
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrOpenOfflineObj
api_type:
- HeaderDef
ms.assetid: cee1a940-fe01-d364-5d7c-c9e9dfeb8979
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: ac6584819b5dfa96a5f7816f1d77b89323e3eaf8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791955"
---
# <a name="hropenofflineobj"></a>HrOpenOfflineObj

  
  
**Betrifft**: Outlook 
  
Öffnet eine offline-Objekt basierend auf einem bestimmten Profil.
  
## <a name="quick-info"></a>QuickInfo

|||
|:-----|:-----|
|Vom exportiert werden:  <br/> |Msmapi32.dll  <br/> |
|Aufgerufen von:  <br/> |Client  <br/> |
|Implementiert von:  <br/> |Outlook  <br/> |
   
```cpp
typedef HRESULT (STDMETHODCALLTYPE HROPENOFFLINEOBJ)( 
      ULONG ulReserved, 
      LPCWSTR pwszProfileNameIn, 
      const GUID* pGUID, 
      const GUID* pReserved, 
      IMAPIOfflineMgr** ppOfflineObj); 

```

## <a name="parameters"></a>Parameter

 _ulReserved_
  
> [in] Dieser Parameter wird nicht verwendet. Es muss 0 sein.
    
 _pwszProfileNameIn_
  
> [in] Der Name des Profils, das für das offline-Objekt ist. Es muss in Unicode ausgedrückt werden. 
    
 _pGUID_
  
> [in] Zeiger auf eine GUID, die verwendet werden kann, um dieses Objekt von anderen Objekten offline eindeutig zu identifizieren. Es muss **GUID_GlobalState**sein.
    
 _Beibehalten_
  
> [in] Dieser Parameter wird nicht verwendet. Es muss **null**sein.
    
 _ppOfflineObj_
  
> [out] Ein Zeiger auf das angeforderte offline-Objekt. Der Aufrufer kann diesen Zeiger verwenden, für den Zugriff auf die [IMAPIOfflineMgr: IMAPIOffline](imapiofflinemgrimapioffline.md) Schnittstelle, die Rückrufe zu erhalten, die dieses Objekt unterstützt und Rückrufe dafür einzurichten. 
    
## <a name="return-values"></a>Rückgabewerte

S_OK 
  
- Der Funktionsaufruf ist erfolgreich.
    
MAPI_E_NOT_FOUND
  
- Fehler beim Aufruf der Funktion.
    
## <a name="remarks"></a>Hinweise

Dies ist der erste Aufruf, den ein Client sendet, wenn der Client über Änderungen Zustand Verbindung für ein bestimmtes Profil benachrichtigt werden möchte. Beim Aufrufen **HrOpenOfflineObj**, erhält der Client eine offline-Objekt, das **IMAPIOfflineMgr**unterstützt. Der Client kann prüfen, ob die Arten von Rückrufe (mithilfe von [IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)) durch das Objekt unterstützt, und klicken Sie dann eingerichtet Rückrufe (mithilfe von [IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)).
  
Wenn [GetProcAddress](http://msdn.microsoft.com/en-us/library/ms683212.aspx) für die Adresse des dieser Funktion in msmapi32.dll suchen, geben Sie **HrOpenOfflineObj@20** als den Namen der Prozedur. 
  
 **HrOpenOfflineObj** funktioniert nur für Clients, die MAPI-Anbieter, COM-Add-Ins und Exchange-Clienterweiterungen innerhalb des Outlook ausgeführt werden. Andernfalls **HrOpenOfflineObj** **MAPI_E_NOT_FOUND**. 
  
## <a name="see-also"></a>Siehe auch



[IMAPIOffline: IUnknown](imapiofflineiunknown.md)
  
[IMAPIOfflineMgr: IMAPIOffline](imapiofflinemgrimapioffline.md)


[Über die Offline State-API](about-the-offline-state-api.md)
  
[MAPI-Konstanten](mapi-constants.md)

