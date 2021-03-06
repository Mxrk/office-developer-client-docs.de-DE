---
title: Bestimmen der Ende einer Tabelle
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c879e972-05f4-4716-8fc2-db5b22f34ca8
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 7cbf11f16948d582ba36a0b4d20411549b723b38
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791533"
---
# <a name="determining-a-tables-end"></a>Bestimmen der Ende einer Tabelle

  
  
**Betrifft**: Outlook 
  
 Ein häufiger Fehler ist, wird davon ausgegangen, dass das Ende der Tabelle erreicht wurde hat: 
  
- [IMAPITable::QueryRows](imapitable-queryrows.md) wurde in einer Schleife, mit dem Ende der Schleife durch die Anzahl der Zeilen von [IMAPITable::GetRowCount](imapitable-getrowcount.md)zurückgegebene bestimmt aufgerufen. Anzahl die **GetRowCount** gibt stellt keine immer die genaue Anzahl der Zeilen in der Tabelle dar; Es ist eine ungefähre Anzahl. 
    
- **QueryRows** mit einer festen Anzahl von Zeilen aufgerufen wurde, und es werden weniger Zeilen zurückgegeben. Erst **QueryRows** ein Rowset mit einer Zeilenanzahl gleich 0 (null), die es keine weiteren Zeilen gibt sind abgerufen wird. 
    
> [!IMPORTANT]
> Die einzige Zeit, die ein Anrufer übernehmen kann, dass sich der Cursor am Ende der Tabelle für eine positive Zeilenanzahl oder am Anfang der Tabelle eine negative Zeilenanzahl befindet ist, wenn der Wert S_OK und keine Zeilen zurückgegeben werden. Der Wert wird nie MAPI_E_NOT_FOUND zurückgegeben. 
  
## <a name="see-also"></a>Siehe auch



[MAPI-Tabellen](mapi-tables.md)

