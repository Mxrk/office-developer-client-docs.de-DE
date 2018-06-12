---
title: ANGLETOPAR-Funktion
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253218
localization_priority: Normal
ms.assetid: 4d87313a-c09a-582c-04f4-d95800e3e9f2
description: Gibt einen transformierten Winkel im Ziel-Shape übergeordneten Koordinatensystem zurück. Konvertiert einen Winkel aus lokalen Koordinaten in einem Quell-Shape in die übergeordneten Koordinaten in einem Ziel-Shape.
ms.openlocfilehash: 3a739c55d568dc548f8175b56f22e6ec4c28e4c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19796408"
---
# <a name="angletopar-function"></a><span data-ttu-id="85ddb-104">ANGLETOPAR Function</span><span class="sxs-lookup"><span data-stu-id="85ddb-104">ANGLETOPAR Function</span></span>

<span data-ttu-id="85ddb-105">Gibt einen transformierten Winkel im Ziel-Shape übergeordneten Koordinatensystem zurück.</span><span class="sxs-lookup"><span data-stu-id="85ddb-105">Returns a transformed angle in the destination shape's parent coordinate system.</span></span> <span data-ttu-id="85ddb-106">Konvertiert einen Winkel aus lokalen Koordinaten in einem Quell-Shape in die übergeordneten Koordinaten in einem Ziel-Shape.</span><span class="sxs-lookup"><span data-stu-id="85ddb-106">Converts an angle from local coordinates in a source shape to the parent coordinates in a destination shape.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="85ddb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="85ddb-107">Syntax</span></span>

<span data-ttu-id="85ddb-108">ANGLETOPAR (** *SrcAngle* **, ** *SrcRef* **, ** *Zielbezug* **)</span><span class="sxs-lookup"><span data-stu-id="85ddb-108">ANGLETOPAR(** *srcAngle* **, ** *srcRef* **, ** *dstRef* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="85ddb-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="85ddb-109">Parameters</span></span>

|<span data-ttu-id="85ddb-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="85ddb-110">**Name**</span></span>|<span data-ttu-id="85ddb-111">**Erforderlich/Optional**</span><span class="sxs-lookup"><span data-stu-id="85ddb-111">**Required/Optional**</span></span>|<span data-ttu-id="85ddb-112">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="85ddb-112">**Data Type**</span></span>|<span data-ttu-id="85ddb-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="85ddb-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="85ddb-114">_srcAngle_</span><span class="sxs-lookup"><span data-stu-id="85ddb-114">_srcAngle_</span></span> <br/> |<span data-ttu-id="85ddb-115">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="85ddb-115">Required</span></span>  <br/> |<span data-ttu-id="85ddb-116">**Numerische**</span><span class="sxs-lookup"><span data-stu-id="85ddb-116">**Numeric**</span></span> <br/> |<span data-ttu-id="85ddb-117">Ein Winkel im Quellkoordinatensystem.</span><span class="sxs-lookup"><span data-stu-id="85ddb-117">An angle in the source coordinate system.</span></span>  <br/> |
| <span data-ttu-id="85ddb-118">_srcRef_</span><span class="sxs-lookup"><span data-stu-id="85ddb-118">_srcRef_</span></span> <br/> |<span data-ttu-id="85ddb-119">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="85ddb-119">Required</span></span>  <br/> |<span data-ttu-id="85ddb-120">**String**</span><span class="sxs-lookup"><span data-stu-id="85ddb-120">**String**</span></span> <br/> | <span data-ttu-id="85ddb-121">Ein Bezug auf eine Zelle im Quellobjekt, beispielsweise ein Shape, eine Gruppe, ein Zeichenblatt usw.</span><span class="sxs-lookup"><span data-stu-id="85ddb-121">A reference to a cell in the source object, such as a shape, group, page, and so on.</span></span>  <br/> |
| <span data-ttu-id="85ddb-122">_Zielbezug_</span><span class="sxs-lookup"><span data-stu-id="85ddb-122">_dstRef_</span></span> <br/> |<span data-ttu-id="85ddb-123">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="85ddb-123">Required</span></span>  <br/> |<span data-ttu-id="85ddb-124">**String**</span><span class="sxs-lookup"><span data-stu-id="85ddb-124">**String**</span></span> <br/> |<span data-ttu-id="85ddb-125">Ein Bezug auf eine Zelle im Zielobjekt, beispielsweise ein Shape, eine Gruppe, ein Zeichenblatt usw.</span><span class="sxs-lookup"><span data-stu-id="85ddb-125">A reference to a cell in the destination object, such as a shape, group, page, and so on.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="85ddb-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="85ddb-126">Remarks</span></span>

<span data-ttu-id="85ddb-p103">Diese Funktion ist auch dann ausführbar, wenn die Ausgangs- und Ziel-Shapes in Gruppen eingebunden sind. Wird ebenfalls für Dreh- und Kippvorgänge in der Zwischentransformation angepasst.</span><span class="sxs-lookup"><span data-stu-id="85ddb-p103">This function works even when the source and destination shapes are within groups. It also adjusts for rotation and flips in the intermediate transformation.</span></span>
  
<span data-ttu-id="85ddb-129">Die Ausgangs- und Zielkoordinaten müssen auf dem gleichen Zeichenblatt sein.</span><span class="sxs-lookup"><span data-stu-id="85ddb-129">The source and destination coordinates must be on the same page.</span></span>
  
<span data-ttu-id="85ddb-130">Wenn das Ziel ein Zeichenblatt ohne übergeordnetes Objekt ist, wird das Ergebnis in den lokalen Koordinaten des Zeichenblatts ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="85ddb-130">If the destination is a page, which has no parent, the result is expressed in page's local coordinates.</span></span>
  
