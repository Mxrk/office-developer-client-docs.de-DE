---
title: IOlkApptRebaserBeginRebaseAppointments
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed50422e-9edf-4b73-1789-340b70532621
description: Beginnt eine neue Aufgabe für neuen Termin Basisadressen anhand einer Liste von Terminen, die in der Regel von IOlkApptRebaser::EndEnumerateAppointmentsabgerufen.
ms.openlocfilehash: 2becb305eebe448e2adecf91c2a111f86d97fe50
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791127"
---
# <a name="iolkapptrebaserbeginrebaseappointments"></a>IOlkApptRebaser::BeginRebaseAppointments

Beginnt eine neue Aufgabe für neuen Termin Basisadressen anhand einer Liste von Terminen, die in der Regel von [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)abgerufen.
  
## <a name="quick-info"></a>QuickInfo

Finden Sie unter [IOlkApptRebaser](iolkapptrebaser.md).
  
```cpp
HRESULT BeginRebaseAppointments( 
    const SRowSet *pRows, 
    PFNREBASETASKPROGRESS pfnProgress, 
    PFNREBASETASKCOMPLETE pfnComplete, 
    void **ppContext);
```

## <a name="parameters"></a>Parameter

_pRows_
  
> [in] Erforderlich. Ein Zeiger auf eine [SRowSet](http://msdn.microsoft.com/library/7e3761be-afd6-46cb-9a08-25e9016c1241%28Office.15%29.aspx) -Struktur, die beschreibt, die Termine, die neuen Basisadressen. Diese Struktur wird in der Regel von einem vorherigen Aufruf von [IOlkApptRebaser::EndEnumerateAppointments](iolkapptrebaser-endenumerateappointments.md)abgerufen.
    
_pfnProgress_
  
> [in] Optional. Ein Zeiger auf ein Rebase-Funktion zum Fortschritt Task Status empfangen. **PFNREBASETASKPROGRESS** wird in tzmovelib.h definiert. 
    
_pfnComplete_
  
> [out] Optional. Ein Zeiger auf eine Funktion Rebase Task Abschluss über Rebase Abschluss benachrichtigt. **PFNREBASETASKCOMPLETE** wird in tzmovelib.h definiert. 
    
_ppContext_
  
> [out] Erforderlich. Ein Zeiger auf einen Zeiger auf den zurückgegebenen Kontext. Dieser Kontext wird in der Regel an [IOlkApptRebaser::EndRebaseAppointments](iolkapptrebaser-endrebaseappointments.md)übergeben werden.
    
## <a name="return-values"></a>Rückgabewerte

S_OK zurück, wenn der Aufruf erfolgreich war; andernfalls einen Fehlercode.
  
## <a name="remarks"></a>Anmerkungen

Diese Aufgabe wird in einem neuen Thread ausgeführt.
  
## <a name="see-also"></a>Siehe auch

- [Zum neuen Basisadressen Kalender programmgesteuert Sommerzeit](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

