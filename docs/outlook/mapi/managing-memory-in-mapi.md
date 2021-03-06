---
title: Verwalten von Arbeitsspeicher in MAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9eee6925-ab91-413e-8907-c747ab4a4bb5
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 5859d94f85ca3fe7a0c738ed596d3c1a11fb2e8d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792916"
---
# <a name="managing-memory-in-mapi"></a>Verwalten von Arbeitsspeicher in MAPI

  
  
**Betrifft**: Outlook 
  
Wissen, wie und wann zum Zuordnen und Freigeben von Arbeitsspeicher ist ein wichtiger Teil der Programmierung mit MAPI. MAPI bietet sowohl Funktionen und Makros, mit denen der Client oder Dienstanbieter kann Speicher einheitlich zu verwalten. Die drei Funktionen sind wie folgt:
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
Wenn Clients und -Dienstanbieter verwenden Sie diese Funktionen, das Problem der "Eigentümer" – weiß, d. h., das Freigeben von – ein bestimmter Block des Speichers wird entfernt. Ein Client Aufrufen einer Service Provider-Methode muss einen Puffer groß genug für ein Rückgabewert beliebiger Größe nicht übergeben. Der Dienstanbieter kann einfach die erforderliche Menge an Arbeitsspeicher mit **MAPIAllocateBuffer** zuweisen und, bei Bedarf **MAPIAllocateMore**und dem Client können später freigegeben werden soll Belieben **MAPIFreeBuffer**, unabhängig von dem Dienst verwenden Anbieter. 
  
Die Arbeitsspeicher-Makros werden verwendet, um die Strukturen oder Arrays von Strukturen mit einer bestimmten Größe zuordnen. Clients und -Dienstanbieter sollten diese Makros verwenden, anstatt Speicher manuell. Beispielsweise wenn ein Client namensauflösung Verarbeitung für eine Empfängerliste mit drei Einträge verarbeiten muss, kann das Makro **SizedADRLIST** verwendet werden so erstellen Sie eine **ADRLIST** -Struktur, mit der richtigen Anzahl an **IAddrBook::ResolveName** übergeben **ADRENTRY** Mitglieder. Alle Makros Speicher sind in der MAPIDEFS definiert. H-Headerdatei. Diese Makros sind: 
  
|||
|:-----|:-----|
|[SizedADRLIST](sizedadrlist.md) <br/> |[SizedDtblPage](sizeddtblpage.md) <br/> |
|[SizedDtblButton](sizeddtblbutton.md) <br/> |[SizedENTRYID](sizedentryid.md) <br/> |
|[SizedDtblCheckBox](sizeddtblcheckbox.md) <br/> |[SizedSPropProblemArray](sizedspropproblemarray.md) <br/> |
|[SizedDtblComboBox](sizeddtblcombobox.md) <br/> |[SizedSPropTagArray](sizedsproptagarray.md) <br/> |
|[SizedDtblEdit](sizeddtbledit.md) <br/> |[SizedSRowSet](sizedsrowset.md) <br/> |
|[SizedDtblGroupBox](sizeddtblgroupbox.md) <br/> |[SizedSSortOrderSet](sizedssortorderset.md) <br/> |
|[SizedDtblLabel](sizeddtbllabel.md) <br/> | <br/> |
   
MAPI unterstützt die Verwendung der COM-Schnittstelle [IMalloc](http://msdn.microsoft.com/en-us/library/ms678425%28VS.85%29.aspx) auch für die Speicherverwaltung. -Dienstanbieter erhalten einen **IMalloc** -Schnittstelle auf MAPI bei der Initialisierung und können auch über die Funktion [MAPIGetDefaultMalloc](mapigetdefaultmalloc.md) abrufen. Der wichtigste Vorteil für die Verwendung der **IMalloc** -Methoden zum Verwalten von Arbeitsspeicher über die MAPI-Funktionen besteht darin, dass mit den Methoden COM möglich, einen vorhandenen Puffer neu zuordnen. Neubelegung unterstützt die Funktionen des MAPI-Speicher nicht. 
  

