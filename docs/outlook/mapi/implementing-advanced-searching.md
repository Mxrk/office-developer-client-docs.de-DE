---
title: Implementieren von Erweiterte Suche
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 4430b52b470b89bd7d81922b98b121b3a455768f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792550"
---
# <a name="implementing-advanced-searching"></a>Implementieren von Erweiterte Suche

  
  
**Betrifft**: Outlook 
  
Einige Address Book Container unterstützt eine erweiterte Suchfunktionen, mit der Clients auf andere Eigenschaften als **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) durchsuchen kann. Zur Unterstützung der erweiterten Suche muss vom Dienstanbieter ein speziellen Containers implementieren, das über die **PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md))-Eigenschaft des Ihrer andere Container zugegriffen werden kann. **PR_SEARCH** enthält ein Container-Objekt, das Zugriff auf eine Tabelle anzeigen bietet, die beschreibt das Dialogfeld zum eingeben und bearbeiten die Kriterien für die erweiterte Suche verwendet. 
  
 **Zur Unterstützung der erweiterten Suche**
  
1. Definieren Sie eine Eigenschaft für die einzelnen von den Suchkriterien.
    
2. Im Abschnitt des Codes in den Container [IMAPIProp::OpenProperty](imapiprop-openproperty.md) -Methode, die **PR_SEARCH** -Eigenschaft behandelt: 
    
1. Überprüfen Sie, dass der Client die Schnittstelle **IMAPIContainer** anfordert. Wenn eine ungeeignete-Schnittstelle angefordert wird, wird ein Fehler auftritt, und geben Sie MAPI_E_INTERFACE_NOT_SUPPORTED zurück. 
    
2. Erstellen Sie ein neues Search-Objekt, das die **IMAPIContainer** -Schnittstelle unterstützt. 
    
3. Zu diesem Zeitpunkt wird Ihre Suche des Containers **IMAPIProp::OpenProperty** -Methode aufgerufen werden, dessen Eigenschaft **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) abzurufen. Vom Dienstanbieter muss eine zeigt die Tabelle, in der Regel durch einen Aufruf von [BuildDisplayTable](builddisplaytable.md), angeben, die Sie im Dialogfeld Erweiterte Suche der Container beschreibt.
    
4. MAPI zeigt das Dialogfeld Suchen an, in dem der Benutzer die entsprechenden Kriterien einzugeben. Wenn der Benutzer beendet wurde, ruft MAPI des Containers [IMAPIProp::SetProps](imapiprop-setprops.md) -Methode, um die Suchkriterien zu speichern. 
    
5. Ein Anruf wird versucht, Ihre Suche des Containers Inhaltstabelle anfordern. Füllen Sie auf Inhaltstabelle, indem Sie alle Einträge im Container, die mit den Kriterien übereinstimmen.
    

