---
title: IMSLogonCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.CompareEntryIDs
api_type:
- COM
ms.assetid: 481812d6-8e94-4510-b288-55501dd5757c
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: c2e6600af66f3dab8ff0fbb5442a1354687a3cbb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792661"
---
# <a name="imslogoncompareentryids"></a>IMSLogon::CompareEntryIDs

  
  
**Betrifft**: Outlook 
  
Vergleicht zwei Eintragsbezeichner, um zu bestimmen, ob sie sich auf dasselbe Objekt verweisen. MAPI verweist dieses Anrufs mit einem Dienstanbieter nur, wenn der eindeutige Bezeichner (UIDs) in beiden Eintragsbezeichner verglichen werden soll, die von diesem Provider behandelt werden.
  
```cpp
HRESULT CompareEntryIDs(
  ULONG cbEntryID1,
  LPENTRYID lpEntryID1,
  ULONG cbEntryID2,
  LPENTRYID lpEntryID2,
  ULONG ulFlags,
  ULONG FAR * lpulResult
);
```

## <a name="parameters"></a>Parameter

 _cbEntryID1_
  
> [in] Die Größe in Bytes für die Eintrags-ID auf das durch den Parameter _lpEntryID1_ _._
    
 _lpEntryID1_
  
> [in] Ein Zeiger auf die erste Eintrags-ID, die verglichen werden.
    
 _cbEntryID2_
  
> [in] Die Größe in Bytes für die Eintrags-ID auf das durch den Parameter _lpEntryID2_ _._
    
 _lpEntryID2_
  
> [in] Ein Zeiger auf die zweite Eintrags-ID, die verglichen werden.
    
 _ulFlags_
  
> [in] Reserviert. NULL muss sein.
    
 _lpulResult_
  
> [out] Ein Zeiger auf das zurückgegebene Ergebnis des Vergleichs. True, wenn die zwei-Eintragsbezeichner auf dasselbe Objekt verweisen. andernfalls, FALSE.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Aufruf erfolgreich ausgef�hrt und der erwartete Wert oder Werte zur�ckgegeben hat.
    
## <a name="remarks"></a>Hinweise

Nachricht-Anbieter implementiert die **IMSLogon::CompareEntryIDs** -Methode zum Vergleichen von zwei Eintragsbezeichner für einen bestimmten Eintrag in einem Nachrichtenspeicher, um zu bestimmen, ob sie sich auf dasselbe Objekt verweisen. Wenn die zwei-Eintragsbezeichner auf dasselbe Objekt verweisen, wird **CompareEntryIDs** den _LpulResult_ -Parameter auf true festgelegt; Wenn sie auf verschiedene Objekte verweisen, wird **CompareEntryIDs** _LpulResult_ auf false festgelegt. 
  
 **CompareEntryIDs** ist hilfreich, da ein Objekt mehr als eine gültige Eingabe Bezeichner haben kann. Dies kann beispielsweise vorkommen, nach der Installation einer neuen Version des Anbieters einer Nachricht. 
  
## <a name="see-also"></a>Siehe auch



[IMSLogon: IUnknown](imslogoniunknown.md)

