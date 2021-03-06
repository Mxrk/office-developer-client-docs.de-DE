---
title: ISocialProviderVersion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dfc92878-ab8b-4721-aee8-997c56a8e45b
description: Gibt eine Zeichenfolge, die die Versionsnummer des Anbieters für diese für soziale Netzwerke darstellt.
ms.openlocfilehash: 5c82df2dc4c052b1a06bcecb16defbb4dee38b18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795980"
---
# <a name="isocialproviderversion"></a>ISocialProvider::Version

Gibt eine Zeichenfolge, die die Versionsnummer des Anbieters für diese für soziale Netzwerke darstellt. 
  
```cpp
[propget] HRESULT _stdcall Version([out, retval] BSTR* Version);
```

## <a name="property-value"></a>Eigenschaftswert

Eine Zeichenfolge, die die Versionsnummer des Anbieters enthält.
  
## <a name="remarks"></a>Hinweise

Die Versionszeichenfolge sollten die _Hauptversion_verwenden. _MinorVersion_ -Format (beispielsweise 1.4730). 
  
## <a name="see-also"></a>Siehe auch

- [ISocialProvider: IUnknown](isocialprovideriunknown.md)

