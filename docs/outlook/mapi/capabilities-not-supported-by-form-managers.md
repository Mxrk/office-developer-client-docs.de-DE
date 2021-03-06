---
title: Funktionen, die vom Formular-Manager nicht unterstützt
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b51e9e03-a333-4fdc-b6fe-87bd4e947b9f
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 86c91353b620482ca0862aa998aae1b3329cfc94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791371"
---
# <a name="capabilities-not-supported-by-form-managers"></a>Funktionen, die vom Formular-Manager nicht unterstützt

  
  
**Betrifft**: Outlook 
  
Die folgenden Features werden von der Standard-Formular-Manager aus Gründen der Systemleistung nicht unterstützt, aber können benutzerdefiniertes Formular-Manager unterstützt werden.
  
- Eine Hierarchie, mit die Formulare gruppiert oder in einer Formularbibliothek kategorisiert werden kann. Eine Formularbibliothek bietet eine Flatfile Datenbank von Formularen.
    
- Steuerung des Zugriffs für Kategorien von Formularen, Nachrichtenklassen oder Klassen entspricht.
    
- Unterstützung für mehrere Sprachversionen desselben Formulars in einer einzelnen Formularbibliothek.
    
Dies sind die Implementierungsprobleme. Es gibt nichts zu verhindern, dass einen benutzerdefiniertes Formular-Manager Implementieren dieser Features.
  
Die MAPI-Formular-Architektur bietet keine Unterstützung für mehrere Formular-Manager werden gleichzeitig ausgeführt. Obwohl MAPI mehrere gleichzeitige Nachricht-Anbieter, Transport Provider und adressbuchanbietern implementierte unterstützt, wird nur ein einzelnes Formular-Manager unterstützt.
  
Da nur ein Formular-Manager auf einmal ausgeführt werden kann, wenn Sie einen benutzerdefiniertes Formular-Manager implementieren müssen Sie alle Funktionen aus der Standard-Formular-Manager erneut zu implementieren, die Sie benötigen. Da Ihr benutzerdefiniertes Formular-Manager den Standard-Formular-Manager vollständig ersetzt werden sollen, werden Funktionen von der Standard-Formular-Manager nicht verfügbar, es sei denn, sie in Ihrem benutzerdefinierten Formular-Manager dupliziert werden.
  
## <a name="see-also"></a>Siehe auch



[MAPI-Formulare](mapi-forms.md)

