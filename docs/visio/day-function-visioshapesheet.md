---
title: DAY Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251415
localization_priority: Normal
ms.assetid: 3b0842ae-6893-2d7b-6cb2-8905198fae30
description: Gibt eine ganze Zahl von 1 bis 31 für den Tag in Datetime oder Expression zurück. Die DAY-Funktion verwendet den gregorianischen Kalender.
ms.openlocfilehash: 07607b809aec9f50ae8981476313fc5e8dbc3423
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19796821"
---
# <a name="day-function-visioshapesheet"></a>DAY Function (VisioShapeSheet)

Gibt eine ganze Zahl von 1 bis 31 für den Tag in _Datetime_ oder _Expression_zurück. Die DAY-Funktion verwendet den gregorianischen Kalender.
  
## <a name="syntax"></a>Syntax

Tag ("** *Datetime* **" | ** *Ausdruck* ** [, ** *Lcid* **]) 
  
### <a name="parameters"></a>Parameter

|**Name**|**Erforderlich/Optional**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| _DateTime_ <br/> |Erforderlich  <br/> |**String** <br/> |Beliebige Zeichenfolge, die allgemein als Datums- und Zeitangabe erkannt wird, oder ein Bezug auf eine Zelle mit einer Datums- und Zeitangabe.  <br/> |
| _expression_ <br/> |Erforderlich  <br/> |**String** <br/> |Beliebiger Ausdruck, der eine Datums- und Zeitangabe liefert.  <br/> |
| _lcid_ <br/> |Optional  <br/> |**Nummer** <br/> |Gibt den lokalen Bezeichner an, der bei der Auswertung eines nicht lokalen Werts für datetime verwendet werden soll. Der lokale Bezeichner ist eine Zahl, die in den Systemkopfdateien beschrieben wird.  <br/> |
   
### <a name="return-value"></a>R�ckgabewert

Integer
  
## <a name="remarks"></a>Hinweise

Alle Zeitkomponenten in _Datetime_ oder _Expression_ wird verworfen. 
  
Keine Rundung erfolgt. Wenn _Datetime_ nicht vorhanden ist oder nicht in ein gültiges Ergebnis konvertiert werden kann, gibt die Funktion einen Fehler zurück. 
  
Die DAY-Funktion nimmt auch einen einzelnen Zahlenwert für _Expression_ , wobei der Ganzzahlteil des Ergebnisses für die Anzahl von Tagen seit dem 30. Dezember 1899 steht. 
  
## <a name="example-1"></a>Beispiel 1

DAY("30. Mai 1997 15:45:24")
  
Gibt 30 zurück.
  
## <a name="example-2"></a>Beispiel 2

DAY(DATUMSWERT("30. Mai 1997")+7 t.)
  
Gibt 6 zurück.
  
## <a name="example-3"></a>Beispiel 3

DAY(35580.6337)
  
Gibt 30 zurück.
  

