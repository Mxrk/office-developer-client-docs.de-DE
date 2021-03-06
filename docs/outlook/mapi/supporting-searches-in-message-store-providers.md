---
title: Unterstützung für Suchvorgänge in Nachrichtenspeicher Anbietern
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30a3fe28-31ca-4eb8-9353-f75f6d339dc7
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 0cd8bbe14e6af020ec5c93cd46a24853d1c8401c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795679"
---
# <a name="supporting-searches-in-message-store-providers"></a>Unterstützung für Suchvorgänge in Nachrichtenspeicher Anbietern

  
  
**Betrifft**: Outlook 
  
Clientanwendungen weisen häufig einige Benutzeroberflächenkomponenten für die Suche nach Nachrichten in einem Nachrichtenspeicher. Suchkriterien in angegeben sind die [IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md) Schnittstelle mithilfe der Methoden [IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md) und [IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md) . 
  
Clients verwenden die Nachricht Store-Objekt **PR_FINDER_ENTRYID** ([PidTagFinderEntryId](pidtagfinderentryid-canonical-property.md))-Eigenschaft, um den Stammordner des Nachrichtenspeichers zu identifizieren, die Ordnern für die Suchergebnisse. Der Suchergebnisse Ordner ist häufig ein Ordner auf der obersten Ebene des Nachrichtenspeichers, die nicht Teil der Ordnerstruktur IPM und daher ausgeblendet ist.
  
Ob Ihre Nachricht Speicheranbieter einen permanenten Suchergebnisse Ordner verwendet oder einen, erstellt Wenn ein Client die Eintrags-ID in der Eigenschaft **PR_FINDER_ENTRYID** gespeicherten öffnet ist ein Implementierungsdetail. Es ist leichter für Ihre Nachricht Speicheranbieter, einen permanenten Ordner zu verwenden, die erstellt wird, wenn der Nachrichtenspeicher erstellt wurde, da dadurch so vermieden wird, überprüfen Sie die Eintrags-ID, sobald ein beliebiger Ordner geöffnet wird, um festzustellen, ob erstellt die Schwierigkeit ein Suchergebnisse Ordner. Nachricht nicht alle Anbieter können, die jedoch tun. insbesondere, schreibgeschützten Nachrichtenspeicher Speicher, die über einen MAPI-Schnittstelle mit einer Vorversion Datenbank häufig bereitgestellt sind nicht zulässig oder können nicht auf einen Ordner permanent Suchergebnisse in die zugrunde liegende Speichermechanismus zu erstellen. 
  
## <a name="see-also"></a>Siehe auch



[Nachrichtenspeicher-Features](message-store-features.md)

