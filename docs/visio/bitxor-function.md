---
title: BITXOR-Funktion
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251401
localization_priority: Normal
ms.assetid: 672eacaf-a374-c7e2-b39b-8d42d2371aee
description: Gibt eine 16-Bit-Binärzahl in der jedes Bit auf 1 festgelegt ist, wenn das entsprechende Bit in jedoch nicht beide binary Zahl1 und binäre Zahl2 1 ist. Andernfalls wird das Bit auf 0 festgelegt.
ms.openlocfilehash: a0e03258bcfe694dc3bec5469095eff90fb94f1a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19796507"
---
# <a name="bitxor-function"></a>BITXOR Function

Gibt eine 16-Bit-Binärzahl in der jedes Bit auf 1 festgelegt ist, wenn das entsprechende Bit in jedoch nicht beide binary Zahl1 und binäre Zahl2 1 ist. Andernfalls wird das Bit auf 0 festgelegt.
  
## <a name="syntax"></a>Syntax

BITXOR (** *binary Zahl1* **, ** *binary Zahl2* **) 
  
### <a name="parameters"></a>Parameter

|**Name**|**Erforderlich/Optional**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| _binäre Zahl1_ <br/> |Erforderlich  <br/> |**Numerische** <br/> |Die erste 16-Bit-Binärzahl.  <br/> |
| _binäre Zahl2_ <br/> |Erforderlich  <br/> |**Numerische** <br/> |Die zweite 16-Bit-Binärzahl.  <br/> |
   
### <a name="return-value"></a>R�ckgabewert

16-bit Binary
  
## <a name="example"></a>Beispiel

BITXOR(12,6)
  
Gibt 10 zurück. Die Zahl 12 entspricht 0...01100. Die Zahl 6 entspricht 0...00110. Daher ergibt BITXOR(12,6) den Wert 0...0,01010.
  

