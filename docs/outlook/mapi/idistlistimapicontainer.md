---
title: IDistList IMAPIContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IDistList
api_type:
- COM
ms.assetid: bd8e1ddb-3027-428b-8964-81614f80282d
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 7fee3c84d6a4d4a94397f5197f45637b0c7dd2be
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792056"
---
# <a name="idistlist--imapicontainer"></a>IDistList: IMAPIContainer

  
  
**Betrifft**: Outlook 
  
Ermöglicht den Zugriff auf Verteilerlisten änderbare Adresse Adressbuch-Container. **IDistList** können erstellen, kopieren und Löschen von Verteilerlisten, neben dem namensauflösung ausgeführt. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapidefs.h  <br/> |
|Verf�gbar gemacht von:  <br/> |Verteilung List-Objekten  <br/> |
|Implementiert von:  <br/> |Von adressbuchanbietern implementierte  <br/> |
|Aufgerufen von:  <br/> |Clientanwendungen  <br/> |
|Schnittstellenbezeichner:  <br/> |IID_IDistList  <br/> |
|Zeigertyp:  <br/> |LPDISTLIST  <br/> |
|Transaktionsmodell:  <br/> |Durchgeführt  <br/> |
   
## <a name="vtable-order"></a>Vtable-Reihenfolge

Diese Schnittstelle hat keinen eindeutigen Methoden.
  
|**Erforderliche Eigenschaften**|**Zugriff**|
|:-----|:-----|
|**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))  <br/> |Lese-/Schreibzugriff  <br/> |
|**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |Lese-/Schreibzugriff  <br/> |
|**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |Schreibgeschützt.  <br/> |
|**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |Schreibgeschützt.  <br/> |
|**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))  <br/> |Schreibgeschützt.  <br/> |
   
## <a name="remarks"></a>Hinweise

Die **IDistList** -Schnittstelle erbt von [IMAPIContainer](imapicontainerimapiprop.md) und enthält die gleichen Methoden als Address Book Container. Aus diesem Grund, da die Methoden der Schnittstelle **IDistList** identisch mit denen der [IABContainer](iabcontainerimapicontainer.md) Schnittstelle sind, sind sie nicht hier nicht dupliziert. 
  
Eine Verteilerliste oder ein Objekt, das **IDistList** implementiert ist eine Auflistung von messaging Benutzerobjekte oder einzelne Empfänger. Eine Verteilerliste kann alle messaging Benutzerobjekte oder einige messaging-Benutzer und einige Verteilerlisten bestehen. 
  
Es sind in der Regel zwei Arten von Verteilerlisten:
  
- Verteilerlisten, die von der zugrunde liegenden messaging-System erweitert werden. Diese Art der Liste hat eine Adresse **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) und ist gleich behandelt, als ob es sich um einen einzelnen Empfänger. 
    
- Verteilerlisten, die in einem lokalen Container vorhanden und werden von der Clientanwendung erweitert.
    
Die folgenden: Eigenschaften von optional Verteilerlisten
  
- **PR_LAST_MODIFICATION_TIME** ([PidTagLastModificationTime](pidtaglastmodificationtime-canonical-property.md))
    
- **PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 
    
- **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 
    
Beachten Sie, dass **PR_ADDRTYPE** erforderlich ist, aber **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) nicht. Dies liegt daran eine Verteilerliste, ohne eine e-Mail-Adresse kann weiterhin Nachrichten empfangen, aber die Mitgliederliste erweitert werden muss. Wenn die **PR_ADDRTYPE** -Eigenschaft auf MAPIPDL festgelegt ist, führt MAPI die Erweiterung. Wenn **PR_ADDRTYPE** einen anderen Wert als MAPIPDL ist, führt der Adressbuchhierarchie die Erweiterung. 
  
Weitere Informationen dazu, wie Sie die Referenz-Einträge für die parallelen Methoden des **IABContainer**finden Sie die **IDistList** -Methoden verwenden.
  
## <a name="see-also"></a>Siehe auch



[MAPI-Schnittstellen](mapi-interfaces.md)

