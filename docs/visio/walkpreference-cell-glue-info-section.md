---
title: Zelle "WalkPreference" (Abschnitt "Glue Info")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1115
localization_priority: Normal
ms.assetid: 08165195-7e4e-f3ab-fa76-fbcacb0a9c9c
description: Bestimmt, ob ein Endpunkt eines 1D-Shapes zu einem horizontalen oder vertikalen Verbindungspunkt auf dem Shape, mit dem er dynamisch verbunden ist, verschoben wird, wenn das Shape an eine mehrdeutige Position verschoben wird. Standardmäßig werden beide Endpunkte des 1D-Shapes zu horizontalen Verbindungspunkten verschoben.
ms.openlocfilehash: cd64a67de6ec914ad1bde86cdac829f6c12cebe4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19798404"
---
# <a name="walkpreference-cell-glue-info-section"></a><span data-ttu-id="394b5-104">WalkPreference Cell (Glue Info Section)</span><span class="sxs-lookup"><span data-stu-id="394b5-104">WalkPreference Cell (Glue Info Section)</span></span>

<span data-ttu-id="394b5-p102">Bestimmt, ob ein Endpunkt eines 1D-Shapes zu einem horizontalen oder vertikalen Verbindungspunkt auf dem Shape, mit dem er dynamisch verbunden ist, verschoben wird, wenn das Shape an eine mehrdeutige Position verschoben wird. Standardmäßig werden beide Endpunkte des 1D-Shapes zu horizontalen Verbindungspunkten verschoben.</span><span class="sxs-lookup"><span data-stu-id="394b5-p102">Determines whether an endpoint of a 1-D shape moves to a horizontal or vertical connection point on the shape it is glued to, using dynamic glue, when the shape is moved to an ambiguous position. By default, both endpoints of the 1-D shape move to horizontal connection points.</span></span>
  
|<span data-ttu-id="394b5-107">**Wert**</span><span class="sxs-lookup"><span data-stu-id="394b5-107">**Value**</span></span>|<span data-ttu-id="394b5-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="394b5-108">**Description**</span></span>|<span data-ttu-id="394b5-109">**Automatisierungskonstante**</span><span class="sxs-lookup"><span data-stu-id="394b5-109">**Automation constant**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="394b5-110">1</span><span class="sxs-lookup"><span data-stu-id="394b5-110">1</span></span>  <br/> | <span data-ttu-id="394b5-111">Der Anfangspunkt des 1D-Shapes wird zu einem vertikalen Verbindungspunkt verschoben, der Endpunkt hingegen zu einem horizontalen Verbindungspunkt (Verbindungen von oben zur Seite oder von unten zur Seite).</span><span class="sxs-lookup"><span data-stu-id="394b5-111">The begin point of the 1-D shape moves to a vertical connection point, and the endpoint moves to a horizontal connection point (top-to-side or bottom-to-side connections).</span></span>  <br/> |<span data-ttu-id="394b5-112">**visWalkPrefBegNS**</span><span class="sxs-lookup"><span data-stu-id="394b5-112">**visWalkPrefBegNS**</span></span> <br/> |
| <span data-ttu-id="394b5-113">2</span><span class="sxs-lookup"><span data-stu-id="394b5-113">2</span></span>  <br/> | <span data-ttu-id="394b5-114">Der Anfangspunkt des 1D-Shapes wird zu einem horizontalen Verbindungspunkt verschoben, der Endpunkt hingegen zu einem vertikalen Verbindungspunkt (Verbindungen von der Seite nach oben oder von der Seite nach unten).</span><span class="sxs-lookup"><span data-stu-id="394b5-114">The begin point of the 1-D shape moves to a horizontal connection point, and the endpoint moves to a vertical connection point (side-to-top or side-to-bottom connections).</span></span>  <br/> |<span data-ttu-id="394b5-115">**visWalkPrefEndNS**</span><span class="sxs-lookup"><span data-stu-id="394b5-115">**visWalkPrefEndNS**</span></span> <br/> |
   
## <a name="remarks"></a><span data-ttu-id="394b5-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="394b5-116">Remarks</span></span>

<span data-ttu-id="394b5-p103">Diese Zelle hat keine Auswirkungen auf dynamische Verbinder. Das Verhalten eines dynamischen Verbinders wird von dessen Routingformat bestimmt. Das standardmäßige Routingformat für dynamische Verbinder auf einem Zeichenblatt finden Sie in der Zelle AnordnungFormat. Das Routingformat für einen spezifischen dynamischen Verbinder finden Sie hingegen in der Zelle ShapeAnordnungFormat.</span><span class="sxs-lookup"><span data-stu-id="394b5-p103">This cell has no effect on dynamic connectors. A dynamic connector's behavior is determined by its routing style. See the RouteStyle cell for the default routing style for dynamic connectors on a page, or the ShapeRouteStyle for the routing style of a particular dynamic connector.</span></span>
  
<span data-ttu-id="394b5-120">Wenn Sie einen Verweis auf die Zelle WalkPreference nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft erhalten möchten, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="394b5-120">To get a reference to the WalkPreference cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="394b5-121">Zellenname:</span><span class="sxs-lookup"><span data-stu-id="394b5-121">Cell name:</span></span>  <br/> | <span data-ttu-id="394b5-122">WalkPreference</span><span class="sxs-lookup"><span data-stu-id="394b5-122">WalkPreference</span></span>  <br/> |
   
<span data-ttu-id="394b5-123">Wenn Sie einen Verweis auf die Zelle WalkPreference aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten:</span><span class="sxs-lookup"><span data-stu-id="394b5-123">To get a reference to the WalkPreference cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="394b5-124">Abschnittsindex:</span><span class="sxs-lookup"><span data-stu-id="394b5-124">Section index:</span></span>  <br/> |<span data-ttu-id="394b5-125">**Konstanten visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="394b5-125">**visSectionObject**</span></span> <br/> |
| <span data-ttu-id="394b5-126">Zeilenindex:</span><span class="sxs-lookup"><span data-stu-id="394b5-126">Row index:</span></span>  <br/> |<span data-ttu-id="394b5-127">**visRowMisc**</span><span class="sxs-lookup"><span data-stu-id="394b5-127">**visRowMisc**</span></span> <br/> |
| <span data-ttu-id="394b5-128">Zellenindex:</span><span class="sxs-lookup"><span data-stu-id="394b5-128">Cell index:</span></span>  <br/> |<span data-ttu-id="394b5-129">**visWalkPref**</span><span class="sxs-lookup"><span data-stu-id="394b5-129">**visWalkPref**</span></span> <br/> |
   
