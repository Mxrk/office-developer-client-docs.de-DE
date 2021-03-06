---
title: Zelle "SelectMode" (Abschnitt "Group Properties")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm875
localization_priority: Normal
ms.assetid: 5ba68e05-f394-d7b7-390d-f0a9fdad011e
description: Bestimmt, wie Sie ein Gruppen-Shape und dessen Mitglieder auswählen.
ms.openlocfilehash: 426b4a18bbd54887e4f60b92860a6c3846386671
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797986"
---
# <a name="selectmode-cell-group-properties-section"></a>SelectMode Cell (Group Properties Section)

Bestimmt, wie Sie ein Gruppen-Shape und dessen Mitglieder auswählen.
  
|**Wert**|**Auswahlmodus**|**Automatisierungskonstante**|
|:-----|:-----|:-----|
|0  <br/> |Nur das Gruppen-Shape auswählen.  <br/> |**visGrpSelModeGroupOnly** <br/> |
|1  <br/> |Das Gruppen-Shape zuerst auswählen.  <br/> |**visGrpSelModeGroup1st** <br/> |
|2  <br/> |Mitglieder der Gruppe zuerst auswählen.  <br/> |**visGrpSelModeMembers1st** <br/> |
   
## <a name="remarks"></a>Hinweise

Sie können diesen Wert auch im Dialogfeld **Verhalten** festlegen (mit das Gruppen-Shape ausgewählt haben, klicken Sie auf der Registerkarte [Entwicklertools](run-in-developer-mode-display-the-developer-tab.md) in der Gruppe **Shape-Design** auf **Verhalten**und klicken Sie dann auf einen Modus in der Liste **Auswahl** unter **Gruppe Verhalten** ). 
  
Wenn Sie einen Verweis auf die Zelle SelectMode nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft erhalten möchten, verwenden Sie Folgendes: 
  
|||
|:-----|:-----|
|Zellenname:  <br/> |SelectMode  <br/> |
   
Wenn Sie einen Verweis auf die Zelle SelectMode aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
|Abschnittsindex:  <br/> |**Konstanten visSectionObject** <br/> |
|Zeilenindex:  <br/> |**visRowGroup** <br/> |
|Zellenindex:  <br/> |**visGroupSelectMode** <br/> |
   

