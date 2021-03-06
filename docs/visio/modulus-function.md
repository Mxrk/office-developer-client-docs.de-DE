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
# <a name="modulus-function"></a>MODULUS-Funktion

Gibt den Rest (Modulo), der entsteht, wenn eine Zahl durch einen Divisor geteilt wird.
  
## <a name="syntax"></a>Syntax

Modulo (** *Anzahl* **, ** *Divisor* **) 
  
### <a name="parameters"></a>Parameter

|**Name**|**Erforderlich/Optional**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| _Anzahl_ <br/> |Erforderlich  <br/> |**Nummer** <br/> |Der Dividend.  <br/> |
| _Divisor_ <br/> |Erforderlich  <br/> |**Nummer** <br/> |Der Divisor.  <br/> |
   
### <a name="return-value"></a>R�ckgabewert

Zahl
  
## <a name="remarks"></a>Bemerkungen

Das Ergebnis hat das gleiche Vorzeichen wie der Divisor. Wenn der Divisor 0 ist, wird der Fehler #DIV/0! zurückgegeben. 
  
In fast allen Situationen sollte die MODULUS-Funktion gegenüber der MOD-Funktion verwendet werden. 
  
## <a name="example-1"></a>Beispiel 1

MODULUS(5, 1,4)
  
Gibt 0,8 zurück.
  
## <a name="example-2"></a>Beispiel 2

MODULUS(5, -1,4)
  
Gibt -0,6 zurück.
  
## <a name="example-3"></a>Beispiel 3

MODULUS(-5, 1,4)
  
Gibt 0,6 zurück.
  
## <a name="example-4"></a>Beispiel 4

MODULUS(-5, -1,4)
  
Gibt -0,8 zurück.
  

