---
title: Zelle "DrawingScaleType" (Abschnitt "Page Properties")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm270
localization_priority: Normal
ms.assetid: 5d4f1cf8-bc1f-07b8-1da5-7253808e337e
description: Legt den im Dialogfeld Seite einrichten ausgewählten Zeichnungsmaßstab fest (klicken Sie auf der Registerkarte Start auf den Pfeil neben Seite einrichten).
ms.openlocfilehash: b93bd95a30fe5a8a5de15a8e5ea104279cf1bcda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19796908"
---
# <a name="drawingscaletype-cell-page-properties-section"></a>DrawingScaleType Cell (Page Properties Section)

Legt den im Dialogfeld **Seite einrichten** ausgewählten Zeichnungsmaßstab fest (klicken Sie auf den Pfeil neben **Seite einrichten** auf der Registerkarte **Start** ). 
  
|**Wert**|**Beschreibung**|**Automatisierungskonstante**|
|:-----|:-----|:-----|
| 0  <br/> | Kein Maßstab  <br/> |**visNoScale** <br/> |
| 1  <br/> | Architekturmaßstab  <br/> |**visArchitectural** <br/> |
| 2  <br/> | Tiefbaumaßstab  <br/> |**visEngineering** <br/> |
| 3  <br/> | Benutzerdefinierter Maßstab  <br/> |**visScaleCustom** <br/> |
| 4  <br/> | Metrisch  <br/> |**visScaleMetric** <br/> |
| 5  <br/> | Maschinenbaumaßstab  <br/> |**visScaleMechanical** <br/> |
   
## <a name="remarks"></a>Hinweise

Wenn Sie einen Verweis auf die Zelle DrawingScaleType nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft erhalten möchten, verwenden Sie Folgendes: 
  
|||
|:-----|:-----|
| Zellenname:  <br/> | DrawingScaleType  <br/> |
   
Wenn Sie einen Verweis auf die Zelle DrawingScaleType aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
| Abschnittsindex:  <br/> |**Konstanten visSectionObject** <br/> |
| Zeilenindex:  <br/> |**visRowPage** <br/> |
| Zellenindex:  <br/> |**visPageDrawScaleType** <br/> |
   

