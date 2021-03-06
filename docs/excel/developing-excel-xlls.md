---
title: Entwickeln von Excel-XLLs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- -Add-ins - [excel 2007], Entwickeln von XLLs - [Excel 2007], XLLs - [Excel 2007], entwickeln
localization_priority: Normal
ms.assetid: dd27ae4d-ef97-47db-885c-ddd955816900
description: 'Gilt f�r: Excel 2013�| Office 2013�| Visual Studio'
ms.openlocfilehash: cb2483b9cd1b11bcfeee81bba02b6d593e8818fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790403"
---
# <a name="developing-excel-xlls"></a>Entwickeln von Excel-XLLs

**Gilt für**: Excel 2013 | Office 2013 | Visual Studio 
  
Der Hauptgrund f�r das Schreiben von Microsoft Excel XLLs und verwenden der C-API ist die Erstellung von Hochleistungs-Tabellenfunktionen. Die Anwendungsszenarien leistungsstarker Funktionen � und ab Excel 2007 die M�glichkeit, Multithread-Schnittstellen auf leistungsstarke Serverressourcen zu schreiben � machen sie zu einem wichtigen Bestandteil der Excel-Erweiterbarkeit. Die Leistung von XLLs wurde in Excel 2007 durch das Hinzuf�gen neuer Datentypen und die Unterst�tzung von Multithreading weiter verbessert.
  
Die C-API verf�gt nicht �ber die leistungsstarken Features zur schnellen Entwicklung von Microsoft Visual Basic for Applications (VBA) �ber COM oder Microsoft .NET Framework. Die Speicherverwaltung ist lediglich rudiment�r, weswegen mehr Verantwortung beim Entwickler liegt. Viele Excel-Features, die �ber COM durch VBA und .NET Framework verf�gbar sind, sind in der C-API nicht verf�gbar.


- [Excel-Programmierkonzepte](excel-programming-concepts.md)
  
- [Arbeiten mit DLLs](working-with-dlls.md)
  
- [Zugriff auf XLL-Code in Excel (engl.)](accessing-xll-code-in-excel.md)
  
- [Anruf XLL-Funktionen aus der Funktions-Assistenten oder Dialogfelder ersetzen](how-to-call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes.md)
  
- [Aufrufen von Excel von der DLL oder XLL aus](calling-into-excel-from-the-dll-or-xll.md)
  
- [Erstellen von XLLs](creating-xlls.md)
  
- [Auswerten von Namen und andere Arbeitsblatt Formula-Ausdr�cke](evaluating-names-and-other-worksheet-formula-expressions.md)
  
- [Multithreading und Speicherverwaltung](multithreading-and-memory-management.md)
  
- [Asynchrone benutzerdefinierte Funktionen](asynchronous-user-defined-functions.md)
  
- [Clustersichere Funktionen](cluster-safe-functions.md)
  
- [Genehmigungsverfahren Benutzer Zeilenumbr�che in langen Vorg�nge](permitting-user-breaks-in-lengthy-operations.md)
  
- [Anzeigen von Dialogfeldern aus innerhalb einer DLL oder XLL](displaying-dialog-boxes-from-within-a-dll-or-xll.md)
  
- [Zugriff auf Excel-Instanz und im Hauptfenster von Handles](how-to-access-excel-instance-and-main-window-handles.md)
  
- [Abw�rtskompatibilit�t](backward-compatibility.md)
  

