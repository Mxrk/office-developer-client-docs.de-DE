---
title: FBStatus
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: f2d6a11e-847d-6bbe-cd77-e78ee961cb12
description: Eine Enumeration für den Frei/Gebucht-Status Blöcke Frei/Gebucht-Informationen.
ms.openlocfilehash: 67d710f82856dc8ff4839c926018eef88d355f73
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "19790939"
---
# <a name="fbstatus"></a>FBStatus

Eine Enumeration für den Frei/Gebucht-Status Blöcke Frei/Gebucht-Informationen.
  
## <a name="quick-info"></a>QuickInfo

```cpp
enum  
    { 
      fbFree      = 0, 
      fbTentative = fbFree + 1, 
      fbBusy      = fbTentative + 1, 
      fbOutOfOffice = fbBusy + 1 
    }

```

## <a name="remarks"></a>Hinweise

Der Frei/Gebucht-Status eines Textblocks Zeit bestimmt die Anzeige in einem Kalender: **frei**, **gebucht**, **mit Vorbehalt**oder **Abwesend**. 
  
## <a name="see-also"></a>Siehe auch

- [FBBlock_1](fbblock_1.md)
- [IEnumFBBlock::Next](ienumfbblock-next.md)

