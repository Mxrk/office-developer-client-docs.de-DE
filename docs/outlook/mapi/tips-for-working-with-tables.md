---
title: Tipps für das Arbeiten mit Tabellen
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: adb4d589-7e03-4222-8717-898ef397c6b6
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 451bab57d4e2e8669a25d119f9ce28a8f78e628f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795722"
---
# <a name="tips-for-working-with-tables"></a>Tipps für das Arbeiten mit Tabellen

  
  
**Betrifft**: Outlook 
  
Arbeiten mit einem MAPI ist Tabelle etwas like arbeiten mit einer relationalen Datenbank-Tabelle. Ein Benutzer kann die Anzahl der Zeilen und Spalten in der Ansicht und ihre Reihenfolge angeben. Zeilen können abgerufenen jeweils einzeln oder in Gruppen werden. Ein Cursor, das verfolgt die aktuelle Position kann zu einer bestimmten Stelle in der Tabelle verschoben werden. 
  
Zum Arbeiten mit Tabellen Clients verwenden die Schnittstelle schreibgeschützt [IMAPITable: IUnknown](imapitableiunknown.md), während der Dienstanbieter, je nachdem, ob sie die Daten besitzen, die die Tabelle basiert entweder **IMAPITable** verwenden können oder [ITableData: IUnknown](itabledataiunknown.md). Die in diese Schnittstellen definierten Vorgänge können als Vorgänge, die alle Benutzer der Tabellen oder aufgerufen werden können und Vorgänge, die nicht so weit verbreitet verwendet werden, da sie weitergehender kategorisiert werden. Einige der erweiterten Vorgänge sind schwieriger zu implementieren. andere Benutzer sind nicht komplexer, aber für eine kleine kleiner Teil der MAPI-Komponenten von Interesse sind. 
  
Die häufiger Vorgänge sind:
  
- Spalte Vorgänge, die einzelne Spalten beeinflussen. Dazu gehören das Angeben der Eigenschaften enthalten sein, in der Spalte und der Reihenfolge, in der sie eingeschlossen werden sollen.
    
- Zeile Vorgänge, die einzelne Zeilen zu beeinflussen. Abrufen von Daten und die Wartungsvorgänge beinhalten: hinzufügen, löschen und ändern eine einzelne Zeile oder Zeilen.
    
- Globale Vorgänge, die sich auf die gesamte Tabelle auswirken. Dazu gehören ereignisbenachrichtigung, suchen und sortieren.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Tabellen](mapi-tables.md)

