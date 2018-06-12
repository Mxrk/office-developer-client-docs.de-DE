---
title: MODULUS-Funktion
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251465
localization_priority: Normal
ms.assetid: cb6326a5-1bf8-b6a3-5c0d-d38c071353a5
description: Gibt den Rest (Modulo), der entsteht, wenn eine Zahl durch einen Divisor geteilt wird.
ms.openlocfilehash: 4e2ef7acf9dc04e788cb2b8a0ff737f12a79c61a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797530"
---
# <a name="modulus-function"></a><span data-ttu-id="93e23-103">MODULUS-Funktion</span><span class="sxs-lookup"><span data-stu-id="93e23-103">MODULUS Function</span></span>

<span data-ttu-id="93e23-104">Gibt den Rest (Modulo), der entsteht, wenn eine Zahl durch einen Divisor geteilt wird.</span><span class="sxs-lookup"><span data-stu-id="93e23-104">Returns the remainder (modulus) that results when a number is divided by a divisor.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="93e23-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="93e23-105">Syntax</span></span>

<span data-ttu-id="93e23-106">Modulo (** *Anzahl* **, ** *Divisor* **)</span><span class="sxs-lookup"><span data-stu-id="93e23-106">MODULUS(** *number* **, ** *divisor* ** )</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="93e23-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="93e23-107">Parameters</span></span>

|<span data-ttu-id="93e23-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="93e23-108">**Name**</span></span>|<span data-ttu-id="93e23-109">**Erforderlich/Optional**</span><span class="sxs-lookup"><span data-stu-id="93e23-109">**Required/Optional**</span></span>|<span data-ttu-id="93e23-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="93e23-110">**Data Type**</span></span>|<span data-ttu-id="93e23-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="93e23-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="93e23-112">_Anzahl_</span><span class="sxs-lookup"><span data-stu-id="93e23-112">_number_</span></span> <br/> |<span data-ttu-id="93e23-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="93e23-113">Required</span></span>  <br/> |<span data-ttu-id="93e23-114">**Nummer**</span><span class="sxs-lookup"><span data-stu-id="93e23-114">**Number**</span></span> <br/> |<span data-ttu-id="93e23-115">Der Dividend.</span><span class="sxs-lookup"><span data-stu-id="93e23-115">The dividend.</span></span>  <br/> |
| <span data-ttu-id="93e23-116">_Divisor_</span><span class="sxs-lookup"><span data-stu-id="93e23-116">_divisor_</span></span> <br/> |<span data-ttu-id="93e23-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="93e23-117">Required</span></span>  <br/> |<span data-ttu-id="93e23-118">**Nummer**</span><span class="sxs-lookup"><span data-stu-id="93e23-118">**Number**</span></span> <br/> |<span data-ttu-id="93e23-119">Der Divisor.</span><span class="sxs-lookup"><span data-stu-id="93e23-119">The divisor.</span></span>  <br/> |
   
### <a name="return-value"></a><span data-ttu-id="93e23-120">R�ckgabewert</span><span class="sxs-lookup"><span data-stu-id="93e23-120">Return value</span></span>

<span data-ttu-id="93e23-121">Zahl</span><span class="sxs-lookup"><span data-stu-id="93e23-121">Number</span></span>
  
## <a name="remarks"></a><span data-ttu-id="93e23-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="93e23-122">Remarks</span></span>

<span data-ttu-id="93e23-p101">Das Ergebnis hat das gleiche Vorzeichen wie der Divisor. Wenn der Divisor 0 ist, wird der Fehler #DIV/0! zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="93e23-p101">The result has the same sign as the divisor. A #DIV/0! error is returned if the divisor is 0.</span></span> 
  
<span data-ttu-id="93e23-126">In fast allen Situationen sollte die MODULUS-Funktion gegenüber der MOD-Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="93e23-126">In almost all situations, the MODULUS function should be used rather than the MOD function.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="93e23-127">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="93e23-127">Example 1</span></span>

<span data-ttu-id="93e23-128">MODULUS(5, 1,4)</span><span class="sxs-lookup"><span data-stu-id="93e23-128">MODULUS(5, 1.4)</span></span>
  
<span data-ttu-id="93e23-129">Gibt 0,8 zurück.</span><span class="sxs-lookup"><span data-stu-id="93e23-129">Returns 0.8.</span></span>
  
## <a name="example-2"></a><span data-ttu-id="93e23-130">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="93e23-130">Example 2</span></span>

<span data-ttu-id="93e23-131">MODULUS(5, -1,4)</span><span class="sxs-lookup"><span data-stu-id="93e23-131">MODULUS(5, -1.4)</span></span>
  
<span data-ttu-id="93e23-132">Gibt -0,6 zurück.</span><span class="sxs-lookup"><span data-stu-id="93e23-132">Returns -0.6.</span></span>
  
## <a name="example-3"></a><span data-ttu-id="93e23-133">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="93e23-133">Example 3</span></span>

<span data-ttu-id="93e23-134">MODULUS(-5, 1,4)</span><span class="sxs-lookup"><span data-stu-id="93e23-134">MODULUS(-5, 1.4)</span></span>
  
<span data-ttu-id="93e23-135">Gibt 0,6 zurück.</span><span class="sxs-lookup"><span data-stu-id="93e23-135">Returns 0.6.</span></span>
  
## <a name="example-4"></a><span data-ttu-id="93e23-136">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="93e23-136">Example 4</span></span>

<span data-ttu-id="93e23-137">MODULUS(-5, -1,4)</span><span class="sxs-lookup"><span data-stu-id="93e23-137">MODULUS(-5, -1.4)</span></span>
  
<span data-ttu-id="93e23-138">Gibt -0,8 zurück.</span><span class="sxs-lookup"><span data-stu-id="93e23-138">Returns -0.8.</span></span>
  
