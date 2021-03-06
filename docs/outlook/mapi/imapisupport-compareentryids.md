---
title: IMAPISupportCompareEntryIDs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompareEntryIDs
api_type:
- COM
ms.assetid: be6991d9-6353-4838-bc6b-39de51a94d8d
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: c939189c2c8f7d3147c3146f55deac0e032ce9df
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792359"
---
# <a name="imapisupportcompareentryids"></a>IMAPISupport::CompareEntryIDs

  
  
**Betrifft**: Outlook 
  
Vergleicht zwei Eintragsbezeichner, um zu bestimmen, ob sie sich auf dasselbe Objekt verweisen. 
  
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
  
> [in] Die Byteanzahl von in die Eintrags-ID auf den durch den Parameter _lpEntryID1_ verwiesen. 
    
 _lpEntryID1_
  
> [in] Ein Zeiger auf die erste Eintrags-ID, die verglichen werden.
    
 _cbEntryID2_
  
> [in] Die Byteanzahl von in die Eintrags-ID auf den durch den Parameter _lpEntryID2_ verwiesen. 
    
 _lpEntryID2_
  
> [in] Ein Zeiger auf die zweite Eintrags-ID, die verglichen werden.
    
 _ulFlags_
  
> [in] Reserviert. NULL muss sein.
    
 _lpulResult_
  
> [out] Ein Zeiger auf das Ergebnis des Vergleichs. True, wenn die zwei-Eintragsbezeichner auf dasselbe Objekt verweisen. andernfalls, FALSE.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Vergleich war erfolgreich.
    
MAPI_E_UNKNOWN_ENTRYID 
  
> Eine oder beide als Parameter angegebenen Eintrag Bezeichner verweisen nicht auf gültige Objekte möglicherweise, da sie derzeit nicht geöffneten und nicht verfügbar sind.
    
## <a name="remarks"></a>Hinweise

Die **IMAPISupport::CompareEntryIDs** -Methode wird für Adresse Adressbuch und Nachricht Store Anbieter Unterstützungsobjekte implementiert. **CompareEntryIDs** vergleicht zwei Eintragsbezeichner, die mit einem einzelnen Dienstanbieter zu bestimmen, ob sie sich auf dasselbe Objekt verweisen gehören. MAPI extrahiert den [MAPIUID](mapiuid.md) Teil aus den Eintrag-IDs den Dienstanbieter verantwortlich für die Objekte zu bestimmen. MAPI ruft dann **die Anmeldung des Objekts-Eintragsbezeichner zum Durchführen des Vergleichs** . 
  
## <a name="notes-to-callers"></a>Hinweise für Aufrufer

 **CompareEntryIDs** ist hilfreich, da ein Objekt mehr als eine gültige Eingabe Bezeichner haben kann. Dies kann beispielsweise vorkommen, nach der Installation einer neuen Version von einem Dienstanbieter. 
  
Wenn **CompareEntryIDs** einen Fehler zurückgibt, führen Sie keine Aktion basierend auf dem Ergebnis des Vergleichs. In diesem Fall sollten Sie am häufigsten konservative Methode möglich. **CompareEntryIDs** können Fehler auftreten, wenn Sie beispielsweise eine oder beide der Eintragsbezeichner eine ungültige **MAPIUID** Struktur enthalten. 
  
## <a name="see-also"></a>Siehe auch



[MAPIUID](mapiuid.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

