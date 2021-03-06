---
title: IMAPIOfflineSetCurrentState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline.SetCurrentState
api_type:
- COM
ms.assetid: c0aa0df2-79f9-2558-7eb6-accae9bef4b2
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 15e2d5c2aca595c3a06d215cd069c23da3e48125
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792243"
---
# <a name="imapiofflinesetcurrentstate"></a>IMAPIOffline::SetCurrentState

  
  
**Betrifft**: Outlook 
  
Legt den aktuellen Zustand eines offline-Objekts zu online oder offline.
  
```cpp
HRESULT SetCurrentState( 
    ULONG ulFlags, 
    ULONG ulMask, 
    ULONG ulState, 
    void* pReserved 
);
```

## <a name="parameters"></a>Parameter

 _ulFlags_
  
> [in] Ändert das Verhalten dieses Anrufs. Die unterstützten Werte sind:
    
MAPIOFFLINE_FLAG_BLOCK
  
> _UlFlags_ auf diesen Wert festlegen blockiert den Anruf **SetCurrentState** , bis die Änderung der Status abgeschlossen ist. Standardmäßig erfolgt der Übergang asynchron. Beim Übergang asynchron vorliegt, gibt alle **SetCurrentState** Anrufe **E_PENDING** zurück, bis die Änderung abgeschlossen ist. 
    
MAPIOFFLINE_FLAG_DEFAULT
  
> Legt den aktuellen Status ohne zu blockieren.
    
 _ulMask_
  
> [in] Der Teil des Status zu ändern. Der einzige unterstützte Wert ist MAPIOFFLINE_STATE_OFFLINE_MASK.
    
 _ulState_
  
> [in] Der Zustand, zu ändern. Es muss eine der folgenden zwei Werte sein:
    
MAPIOFFLINE_STATE_ONLINE
  
> 
    
MAPIOFFLINE_STATE_OFFLINE
  
> 
    
 _Beibehalten_
  
> Dieser Parameter ist für die Outlook interne Verwendung reserviert und wird nicht unterstützt. 
    
## <a name="return-value"></a>R�ckgabewert

S_OK
  
> Der Status des offline-Objekts wurde erfolgreich geändert wurde.
    
E_PENDING
  
> Dies gibt an, dass der Zustand des offline-Objekts asynchron geändert wird. Dies tritt auf, wenn _UlFlags_ auf MAPIOFFLINE_FLAG_BLOCK in einem früheren **SetCurrentState** Aufruf festgelegt ist, und alle nachfolgender **SetCurrentState** Aufruf diesen Wert, bis zum Abschluss der asynchronen Zustand ändern zurück gibt. 
    
## <a name="see-also"></a>Siehe auch



[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)
  
[IMAPIOffline::GetCurrentState](imapioffline-getcurrentstate.md)


[MAPI-Konstanten](mapi-constants.md)

