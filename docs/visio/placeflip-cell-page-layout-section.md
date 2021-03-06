---
title: Zelle "PlaceFlip" (Abschnitt "Page Layout")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253251
localization_priority: Normal
ms.assetid: df014b98-cfd5-b6d3-4b8a-b0acb3b94412
description: Legt fest, wie platzierbare Shapes kippen und/oder auf einer Seite gedreht werden, wenn Sie das Dialogfeld Layout konfigurieren verwenden (klicken Sie auf der Registerkarte Entwurf in der Gruppe Layout, klicken Sie auf der Seite Re-Layout, und klicken Sie dann auf Weitere Layoutoptionen).
ms.openlocfilehash: fb16849c7a496a4277133c68453d94d6fd2e67f8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797614"
---
# <a name="placeflip-cell-page-layout-section"></a>Zelle "PlaceFlip" (Abschnitt "Page Layout")

Legt fest, wie platzierbare Shapes kippen und/oder auf einer Seite gedreht werden, wenn Sie das Dialogfeld **Layout konfigurieren** verwenden (klicken Sie auf der Registerkarte **Entwurf** in der Gruppe **Layout** , klicken Sie auf **Der Seite Re-Layout**, und klicken Sie dann auf **Weitere Layoutoptionen**).
  
|**Wert**|**Beschreibung**|**Automatisierungskonstante**|
|:-----|:-----|:-----|
|&amp;H0  <br/> |Standard. Nicht kippen.  <br/> |**visLOFlipDefault** <br/> |
|&amp;H1  <br/> |Horizontal kippen.  <br/> |**visLOFlipX** <br/> |
|&amp;H2  <br/> |Vertikal kippen.  <br/> |**visLOFlipY** <br/> |
|&amp;H4  <br/> |In 90-Grad-Schritten kippen.  <br/> |**visLOFlipRotate** <br/> |
|&amp;H8  <br/> |Nicht kippen.  <br/> |**visLOFlipNone** <br/> |
   
## <a name="remarks"></a>Bemerkungen

Der Wert in der Zelle PlaceFlip hilft bei der Ausrichtung eines platzierbaren Shapes in Richtung des nächsten platzierbaren Shapes, mit dem es verbunden ist. Dieser Wert wird normalerweise verwendet, wenn Sie Zeichnungen ausrichten, die statischen Kleber verwenden.
  
Wenn Sie dieses Verhalten für ein bestimmtes Shape festlegen möchten, verwenden Sie die Zelle ShapePlaceFlip im Abschnitt Shape Layout.
  
Zum Abrufen eines Verweises auf die Zelle PlaceFlip nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft, verwenden Sie Folgendes: 
  
|||
|:-----|:-----|
|Zellenname:  <br/> |PlaceFlip  <br/> |
   
Wenn Sie einen Verweis auf die Zelle PlaceFlip aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
|Abschnittsindex:  <br/> |**Konstanten visSectionObject** <br/> |
|Zeilenindex:  <br/> |**visRowPageLayout** <br/> |
|Zellenindex:  <br/> |**visPLOPlaceFlip** <br/> |
   

