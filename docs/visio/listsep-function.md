---
title: LISTSEP-Funktion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251882
localization_priority: Normal
ms.assetid: 73dc5981-2c8c-e76e-e4bd-e65a7c8db242
description: Gibt die Listentrennzeichen Zeichenfolge für das Gebietsschema des aktuellen Benutzers zurück.
ms.openlocfilehash: 77610b2cf3cc515fb5d3e8b4c6c48de98ab4acc2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797346"
---
# <a name="listsep-function"></a>LISTSEP Function

Gibt die Listentrennzeichen Zeichenfolge für das Gebietsschema des aktuellen Benutzers zurück.
  
## <a name="syntax"></a>Syntax

LISTSEP ()
  
### <a name="return-value"></a>R�ckgabewert

String
  
## <a name="example"></a>Beispiel

SETF(GETREF(User.Extent), "MAX (Breite" &amp; LISTENTRENNZ() &amp; "(Höhe)") 
  

