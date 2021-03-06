---
title: Zelle "Type / C" (Abschnitt "Connection Points")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251723
localization_priority: Normal
ms.assetid: 2264d026-2041-3855-2b23-553ce67ae69d
description: Legt den Verbindungspunkttyp fest.
ms.openlocfilehash: 12c953a160ab99aad007e9b2bb9089d651aee553
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19798331"
---
# <a name="type--c-cell-connection-points-section"></a>Type / C Cell (Connection Points Section)

Legt den Verbindungspunkttyp fest.
  
|**Wert**|**Typ**|**Automatisierungskonstante**|
|:-----|:-----|:-----|
|0  <br/> |Nach innen  <br/> |**visCnnctTypeInward** <br/> |
|1  <br/> |Nach außen  <br/> |**visCnnctTypeOutward** <br/> |
|2  <br/> |Nach innen &amp; nach außen  <br/> |**visCnnctTypeInwardOutward** <br/> |
   
## <a name="remarks"></a>Hinweise

Sie können den Verbindungspunkttyp auch festlegen, indem **die Verbinder** auswählen, indem ein Shape und klicken Sie dann mit der rechten Maustaste eines Verbindungspunkts. Zu diesem Zweck müssen Sie im [Entwicklermodus](run-in-developer-mode-display-the-developer-tab.md) ausführen. 
  
Ein Verweis auf den Typ / C Zelle nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft verwenden: 
  
|||
|:-----|:-----|
|Zellenname:  <br/> |Verbindungen.Typ [ *i* ] wobei *i* = < 1 >, 2, 3...  <br/> |
   
Ein Verweis auf den Typ / Zelle C aus einem Programm nach Index verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
|Abschnittsindex:  <br/> |**visSectionConnectionPts** <br/> |
|Zeilenindex:  <br/> |**VisRowConnectionPts** +  *i* wobei *i* = 0, 1, 2...  <br/> |
|Zellenindex:  <br/> |**visCnnctType** (nicht erweiterte Zeilen) **visCnnctC** (erweiterte Zeilen)  <br/> |
   
Informationen zu erweiterten und nicht erweiterten Zeilen finden Sie in der Zeile Connections Points.
  

