---
title: UlValidateParms
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlValidateParms
api_type:
- COM
ms.assetid: 02c66b46-1f01-43fb-832c-bac27aaae19f
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 12b1655b1e6786d2ebc985e834b635679e59f7d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795789"
---
# <a name="ulvalidateparms"></a>UlValidateParms

  
  
**Betrifft**: Outlook 
  
Ruft eine interne Funktion, um zu überprüfen, dass die Parameter-Clientanwendungen zu Dienstanbietern und MAPI-vergangen sind. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapival.h  <br/> |
|Implementiert von:  <br/> |MAPI  <br/> |
|Aufgerufen von:  <br/> |Dienstanbieter  <br/> |
   
```cpp
HRESULT UlValidateParms(
  METHODS eMethod,
  LPVOID First
);
```

## <a name="parameters"></a>Parameter

 _eMethod_
  
> [in] Gibt den-Enumeration zurück, die-Methode, um zu überprüfen. 
    
 _Erster_
  
> [in] Zeiger auf das erste Argument im Stapel.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Aufruf erfolgreich ausgef�hrt und der erwartete Wert oder Werte zur�ckgegeben hat. 
    
MAPI_E_CALL_FAILED 
  
> Ein Fehler verhindert den Abschluss des Vorgangs.
    
## <a name="remarks"></a>Hinweise

Übergeben Sie Parameter zwischen MAPI- und Service Provider wird angenommen, dass korrekt und unterzogen werden nur Debug Validierung mit dem Makro [CheckParms](checkparms.md) . Anbieter sollten alle von Clientanwendungen übergebenen Parameter überprüfen, aber Clients sollten davon ausgehen, dass MAPI und Anbieter Parameter richtig sind. Verwenden Sie das Makro **HR_FAILED** , um Rückgabewerte testen. 
  
Das Makro **UlValidateParms** wird je nachdem, ob der aufrufende Code C oder C++ ist anders aufgerufen. Dieses Makro wird verwendet, um die Parameter für die einige **IUnknown** und MAPI-Methoden, die ULONG anstelle von HRESULT-Werte zurückgeben. das Makro [ValidateParms](validateparms.md) funktioniert für alle anderen. 
  

