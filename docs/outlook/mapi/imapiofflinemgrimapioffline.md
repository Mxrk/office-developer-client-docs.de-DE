---
title: IMAPIOfflineMgr IMAPIOffline
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineMgr
api_type:
- COM
ms.assetid: 3e430308-190c-c9bb-fffc-c26ffecb73a5
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 644fad96c8aec3701233351469a84ef93341b397
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792268"
---
# <a name="imapiofflinemgr--imapioffline"></a>IMAPIOfflineMgr: IMAPIOffline

  
  
**Betrifft**: Outlook 
  
Registrieren für Benachrichtigung Rückrufe zum Ändern eines Benutzerkontos unterstützt.
  
|||
|:-----|:-----|
|Vom exportiert werden:  <br/> |Msmapi32.dll  <br/> |
|Implementiert von:  <br/> |Outlook  <br/> |
|Aufgerufen von:  <br/> |Client  <br/> |
|Schnittstellenbezeichner:  <br/> |IID_IMAPIOfflineMgr  <br/> |
   
## <a name="vtable-order"></a>Vtable-Reihenfolge

|||
|:-----|:-----|
|[Beraten](imapiofflinemgr-advise.md) <br/> |Für Benachrichtigung Rückrufe zum Wechsel Verbindung registriert.  <br/> |
|[Heben Sie diesen Vorgang](imapiofflinemgr-unadvise.md) <br/> |Entfernt die Registrierung ein bestimmtes für Benachrichtigung Rückrufe.  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
| *Platzhalter-member*  <br/> | *Dieser Member ist ein Platzhalter und wird nicht unterstützt.*  <br/> |
   
## <a name="remarks"></a>Hinweise

Beim Öffnen einer offline-Objekt für ein Benutzerprofil-Konto mithilfe von **[HrOpenOfflineObj](hropenofflineobj.md)**, erhält ein Client eine offline-Objekt, das **IMAPIOfflineMgr**unterstützt. 
  
Da diese Schnittstelle von **[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)** erbt, kann der Client (mithilfe von **[QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)** ) diese Schnittstelle Abfragen um ein Objekt abzurufen, die **[IMAPIOffline](imapiofflineiunknown.md)** unterstützt. Der Client kann dann erfahren Sie mehr über die Funktionen der Rückruf des offline-Objekts (von der aufrufenden **[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)** ) und Rückrufe einrichten (mithilfe von **IMAPIOfflineMgr::Advise** ). 
  
Die meisten der Elemente in dieser Schnittstelle sind Platzhalter für die interne Verwendung von Outlook reserviert und kann geändert werden. Anrufer dieser Schnittstelle müssen Mitglieder Platzhalter verwenden Sie nur als dokumentiert.
  
## <a name="see-also"></a>Siehe auch



[IMAPIOffline: IUnknown](imapiofflineiunknown.md)


[Über die Offline State-API](about-the-offline-state-api.md)
  
[MAPI-Konstanten](mapi-constants.md)
  
[HrOpenOfflineObj](hropenofflineobj.md)
  
[MAPI-Schnittstellen](mapi-interfaces.md)

