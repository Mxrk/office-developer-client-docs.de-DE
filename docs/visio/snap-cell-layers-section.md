---
title: Zelle "Snap" (Abschnitt "Layers")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251355
localization_priority: Normal
ms.assetid: c1b24e45-6f08-686b-b53d-e85fb9087a50
description: Bestimmt, ob andere Shapes an den dem Layer zugeordneten Shapes einrasten können. Die dem Layer zugeordneten Shapes können an anderen Shapes einrasten, andere Shapes jedoch nicht.
ms.openlocfilehash: 7fc684afb67d0454ea5907c08f4f7644d97c7f74
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19798137"
---
# <a name="snap-cell-layers-section"></a>Zelle "Snap" (Abschnitt "Layers")

Bestimmt, ob andere Shapes an den dem Layer zugeordneten Shapes einrasten können. Die dem Layer zugeordneten Shapes können an anderen Shapes einrasten, andere Shapes jedoch nicht.
  
|**Wert**|**Beschreibung**|
|:-----|:-----|
|TRUE  <br/> |Andere Shapes können an den dem Layer zugeordneten Shapes einrasten.  <br/> |
|FALSE  <br/> |Andere Shapes können an den dem Layer zugeordneten Shapes nicht einrasten.  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Sie können auch den Wert dieser Zelle mit der Option **Ausrichten** im Dialogfeld **Layereigenschaften** festlegen (klicken Sie auf der Registerkarte **Start** in der Gruppe **Bearbeiten** , klicken Sie auf **Ebenen**, und klicken Sie dann auf **Layereigenschaften**).
  
Wenn Sie einen Verweis auf die Zelle Snap nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft erhalten möchten, verwenden Sie Folgendes: 
  
|||
|:-----|:-----|
|Zellenname:  <br/> |Layers.Snap [ *i* ] wobei *i* = < 1 >, 2, 3...  <br/> |
   
Wenn Sie einen Verweis auf die Zelle Snap aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
|Abschnittsindex:  <br/> |**visSectionLayer** <br/> |
|Zeilenindex:  <br/> |**VisRowLayer** +  *i* wobei *i* = 0, 1, 2...  <br/> |
|Zellenindex:  <br/> |**visLayerSnap** <br/> |
   

