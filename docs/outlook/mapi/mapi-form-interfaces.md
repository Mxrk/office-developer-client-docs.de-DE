---
title: MAPI-Formulars Schnittstellen
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 611213c9-e758-4366-b193-fc62181d3d1f
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 8452a6e49059dd0912f1efffef7e749afd6cdf6a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792981"
---
# <a name="mapi-form-interfaces"></a>MAPI-Formulars Schnittstellen

  
  
**Betrifft**: Outlook 
  
MAPI definiert die folgenden Schnittstellen, die sich auf die Formulare beziehen.
  
|**Name der Schnittstelle**|**Beschreibung**|
|:-----|:-----|
|[IMAPIForm](imapiformiunknown.md) <br/> |Bearbeiten der Formular-Objekte und Form-Objektbefehle behandelt.  <br/> |
|[IMAPIFormAdviseSink](imapiformadvisesinkiunknown.md) <br/> |Bestimmt, ob das Form-Objekt die nächste Nachricht verarbeiten kann und den nächsten oder vorherigen Zustand des Form-Objekts ändert.  <br/> |
|[IMAPIFormContainer](imapiformcontaineriunknown.md) <br/> |Unterstützt die Installation, Deinstallation und Auflösung von Servern für ein bestimmtes Formular Container Formular.  <br/> |
|[IMAPIFormFactory](imapiformfactoryiunknown.md) <br/> |Unterstützt die Verwendung von Servern konfigurierbar Laufzeit-Formular.  <br/> |
|[IMAPIFormInfo](imapiforminfoimapiprop.md) <br/> |Ermöglicht Clientanwendungen zum Arbeiten mit Eigenschaften, die für eine Nachrichtenklasse spezifisch sind.  <br/> |
|[IMAPIFormMgr](imapiformmgriunknown.md) <br/> |Ermöglicht Clientanwendungen zum Abrufen von Informationen zu Servern Formular, Formular Server aktiviert und Formular Servern im Nachrichtensystem installiert.  <br/> |
|[IMAPIMessageSite](imapimessagesiteiunknown.md) <br/> |Zum Bearbeiten von Formularobjekten zugeordneten Nachrichten verwendet.  <br/> |
|[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) <br/> |Benachrichtigt die Clientanwendungen, die in das Form-Objekt ein Ereignis aufgetreten ist.  <br/> |
|[IMAPIViewContext](imapiviewcontextiunknown.md) <br/> |Zum Reagieren auf Next, Previous und Delete-Befehle in das Form-Objekt verwendet wird.  <br/> |
|[IPersistMessage](ipersistmessageiunknown.md) <br/> |Verwendet, um speichern, initialisieren, und Laden Formularobjekte von und zu speichern.  <br/> |
   
Weitere Informationen zu den Methoden der MAPI-Formulars Schnittstellen finden Sie unter Dokumentation für diese Schnittstellen. Sie müssen nicht alle MAPI-Formulars Schnittstellen implementieren, um ein benutzerdefiniertes Formular erstellen. Ein Formular selbst erfordert nur, dass Sie die **IPersistMessage**, **IMAPIForm**, implementieren und **IMAPIFormAdviseSink** Schnittstellen. Darüber hinaus ist es ratsam, **IMAPIFormFactory** und **IMAPIFormInfo**implementieren. **IMAPIFormFactory** eignet sich für die Einhaltung der OLE und **IMAPIFormInfo** ermöglicht gut geschriebenem Clientanwendungen von Formularen besser zu nutzen. 
  
> [!NOTE]
> Eigentlich ist **IMAPIFormAdviseSink** eine optionale Schnittstelle. Jedoch wird dringend empfohlen, dass Sie es in Ihren Servern Formular implementieren. Diese Schnittstelle ist entscheidend für effiziente Interaktion zwischen messaging-Clients und Servern Formular, insbesondere wenn mehrere Nachrichten Ihres Formulars Servers Klasse die Nachricht wird behandelt werden. 
  
## <a name="see-also"></a>Siehe auch



[MAPI-Formulare](mapi-forms.md)

