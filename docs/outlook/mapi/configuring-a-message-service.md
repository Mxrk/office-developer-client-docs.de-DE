---
title: Konfigurieren einer Nachricht
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d68892e3-7c87-4b3a-a691-bff92f83ed00
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: fd87d169cd5131c6e1c8ca45a35dded96a295c57
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791418"
---
# <a name="configuring-a-message-service"></a>Konfigurieren einer Nachricht

  
  
**Betrifft**: Outlook 
  
 **So konfigurieren Sie die-Dienstanbieter in einem Message-Dienst**
  
- Rufen Sie [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md). Wenn alle Daten für die Konfiguration notwendig sind programmgesteuert verfügbar, können Sie, ob eine Benutzeroberfläche angezeigt werden soll oder nicht. Wenn ein Teil der Informationen für einen oder mehrere Anbieter nicht verfügbar ist, stellen Sie jedoch sicher, dass Sie die Kennzeichen SERVICE_UI_ALLOWED oder SERVICE_UI_ALWAYS festgelegt. Unterdrücken eine Benutzeroberfläche beim erforderlichen Konfigurationsdaten nicht verfügbar Ergebnisse in einem Nachrichtendienst nicht konfiguriert ist.
    
 **So konfigurieren Sie einen einzelnen-Dienstanbieter in einem Message-Dienst**
  
1. Rufen Sie [IMAPISession::GetStatusTable](imapisession-getstatustable.md) Zugriff auf den Dienstanbieter Status-Objekt. 
    
2. Rufen Sie [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) , um den Dienstanbieter Eigenschaftenfenster anzuzeigen. 
    
Weitere Informationen zum Status Objekte verwenden finden Sie unter [Statustabelle und Status-Objekte](status-table-and-status-objects.md).
  

