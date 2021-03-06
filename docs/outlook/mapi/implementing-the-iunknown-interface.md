---
title: Die IUnknown-Schnittstelle implementieren
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01bba63b-a2a1-490e-8b78-5c9ba8d9547b
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 55bf8831af8f78767b2607c21ab54c32f6e4245f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792584"
---
# <a name="implementing-the-iunknown-interface"></a>Die IUnknown-Schnittstelle implementieren

  
  
**Betrifft**: Outlook 
  
Die Methoden für die [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) -Schnittstelle implementiert, die in jedem MAPI-Objekt unterstützt interobject Kommunikation und Objekt Management. 
  
 **IUnknown** verfügt über drei Methoden: [QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx), [IUnknown:: AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)und [IUnknown](http://msdn.microsoft.com/en-us/library/ms682317%28v=VS.85%29.aspx). **QueryInterface** ermöglicht, ein Objekt zu bestimmen, ob ein anderes Objekt eine bestimmte Schnittstelle unterstützt. Mit **QueryInterface**können ohne vorherige Kenntnisse der Funktionalität des jeweils anderen zwei Objekte interagieren. Wenn das Objekt, **das QueryInterface** implementiert, die betreffende-Schnittstelle unterstützt, gibt es einen Zeiger auf die Implementierung der Schnittstelle. Wenn das Objekt die angeforderte Schnittstelle nicht unterstützt, wird den Wert MAPI_E_INTERFACE_NOT_SUPPORTED zurückgegeben. 
  
Wenn **QueryInterface** einen Zeiger angeforderte Schnittstelle zurückgegeben wird, muss auch das neue Objekt Referenzzähler erhöht werden. Ein Objekt Referenzzähler ist einen numerischen Wert verwendet, um das Objekt Lebensdauer verwalten. Bei der Referenzzähler größer als 1 ist, wird der Speicher des Objekts kann nicht freigegeben werden, da sie aktiv verwendet wird. Es ist nur bei der Referenzzähler 0 erreicht, dass das Objekt sicher freigegeben werden kann. 
  
Die anderen beiden **IUnknown** -Methoden, **AddRef** und **Release**, verwalten den Referenzzähler. **AddRef** erhöht den Referenzzähler, während der **Freigabe** dekrementiert es. Alle Methoden oder API-Funktionen, die Schnittstellenzeiger, wie etwa **QueryInterface**, zurückgeben müssen **AddRef** um erhöht den Referenzzähler aufrufen. Alle Implementierungen der Methoden, die Schnittstellenzeiger erhalten müssen aufrufen, **Version** , um die Anzahl der zu verringern, wenn der Mauszeiger nicht mehr benötigt wird. **Version** überprüft einer vorhandenen Referenzzähler den Speicher nur, wenn die Anzahl 0 ist die Schnittstelle zugeordnete freigibt. 
  
> [!NOTE]
> Da **AddRef** und **Release** nicht erforderlich, genaue Werte zurückgeben, müssen Aufrufer dieser Methoden die Rückgabewerte nicht verwenden, um festzustellen, ob ein Objekt noch gültig ist, oder gelöscht wurde wurde. 
  
## <a name="see-also"></a>Siehe auch



[Implementieren von MAPI-Objekten](implementing-mapi-objects.md)

