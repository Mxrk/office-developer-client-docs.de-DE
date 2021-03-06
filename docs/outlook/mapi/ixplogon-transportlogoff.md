---
title: IXPLogonTransportLogoff
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.TransportLogoff
api_type:
- COM
ms.assetid: b2b368ce-4486-4f90-985f-59e50ca95229
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 195f2d718428eb8bb618fc982488c276d8a536da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792891"
---
# <a name="ixplogontransportlogoff"></a>IXPLogon::TransportLogoff

  
  
**Betrifft**: Outlook 
  
Initiiert den Prozess abmelden. 
  
```cpp
HRESULT TransportLogoff(
  ULONG ulFlags
);
```

## <a name="parameters"></a>Parameter

 _ulFlags_
  
> [in] Reserviert. NULL muss sein.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Der Aufruf erfolgreich ausgeführt und der erwartete Wert oder Werte zurückgegeben. Wenn alles andere als S_OK zurückgegeben wird, wird der Anbieter abgemeldet.
    
## <a name="remarks"></a>Hinweise

Die MAPI-Warteschlange die **IXPLogon::TransportLogoff** -Methode aufgerufen, um eine Sitzung Transport Anbieter für einen bestimmten Benutzer zu beenden. Vor dem Aufruf von **TransportLogoff**, verwirft die MAPI-Warteschlange von Daten zu unterstützten messaging-Adresstypen für diese Sitzung in der [IXPLogon::AddressTypes](ixplogon-addresstypes.md) -Methode übergeben. 
  
## <a name="notes-to-implementers"></a>Hinweise für Implementierer

Der Adressbuchhierarchie sollte vorbereitet werden, können Sie jederzeit einen Anruf an **TransportLogoff** akzeptieren kann. Wenn eine Nachricht verarbeitet wird, sollte der Anbieter die sendende Abbrechen. 
  
Der Transportdienst sollte alle Ressourcen für die aktuelle Sitzung freigeben. Wenn es für diese Sitzung mit der Funktion [MAPIAllocateBuffer](mapiallocatebuffer.md) Speicher zugewiesen hat, sollten sie den Arbeitsspeicher freizugeben, mithilfe der [MAPIFreeBuffer](mapifreebuffer.md) -Funktion. Von Speicher vom Transportanbieter zum Aufrufen der Methode [IXPLogon::AddressTypes](ixplogon-addresstypes.md) erfüllen kann zu diesem Zeitpunkt sicher freigegeben werden. 
  
In der Regel für das Gespräch **TransportLogoff** durchführen, sollte ein Anbieter zunächst dessen Anmeldung-Objekt durch Aufrufen der Methode [IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md) ungültig und anschließend wieder seines Support-Objekts. Implementierung der **TransportLogoff** der Anbieter sollte Support-Objekt letzten, freigeben, da beim Support-Objekt veröffentlicht hat, die MAPI-Warteschlange auch das Provider-Objekt selbst freigeben kann. 
  
## <a name="see-also"></a>Siehe auch



[IMAPISupport::MakeInvalid](imapisupport-makeinvalid.md)
  
[IMAPISupport::SpoolerYield](imapisupport-spooleryield.md)
  
[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IXPLogon: IUnknown](ixplogoniunknown.md)

