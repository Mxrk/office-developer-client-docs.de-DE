---
title: IMSLogonLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSLogon.Logoff
api_type:
- COM
ms.assetid: 1b0d1b52-6651-4de3-9381-86772d9d52a1
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 5d9a57cee371675493ba71b2df52b83941d34fc2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792685"
---
# <a name="imslogonlogoff"></a>IMSLogon::Logoff

  
  
**Betrifft**: Outlook 
  
Eine Nachricht Abmeldung Speicheranbieter. 
  
```cpp
HRESULT Logoff(
  ULONG FAR * lpulFlags
);
```

## <a name="parameters"></a>Parameter

 _lpulFlags_
  
> [in] Reserviert. Ein Zeiger auf 0 (null) muss sein.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Aufruf erfolgreich ausgef�hrt und der erwartete Wert oder Werte zur�ckgegeben hat.
    
## <a name="remarks"></a>Hinweise

Nachricht Anbieter implementieren Sie die **IMSLogon::Logoff** -Methode eine Nachricht Speicheranbieter zwangsweise Herunterfahren. **IMSLogon::Logoff** wird in den folgenden Situationen aufgerufen: 
  
- Während MAPI deaktiviert Clientidentität nach einem Aufruf der Methode [IMAPISession::Logoff](imapisession-logoff.md) protokolliert wird. 
    
- Während MAPI aus einer Nachricht Speicheranbieter protokolliert wird. In diesem Fall **IMSLogon::Logoff** im Rahmen der Verarbeitung der [IUnknown](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx) -Methode des Support-Objekts, mit dem Anbieter der Nachricht erstellt, während ein [IMsgStore::StoreLogoff](imsgstore-storelogoff.md) oder **IUnknown verarbeitet wird MAPI aufgerufen wird: Version** Methodenaufruf für eine Nachricht Store-Objekt. 
    
## <a name="see-also"></a>Siehe auch



[IMAPISession::Logoff](imapisession-logoff.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)
  
[IMsgStore::StoreLogoff](imsgstore-storelogoff.md)
  
[IMSProvider::Logon](imsprovider-logon.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMSLogon: IUnknown](imslogoniunknown.md)

