---
title: Konstanten (Frei/Gebucht-API)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ff756bf1-9395-5e50-4f55-1eb0365a84ed
description: Dieses Thema enthält Konstantendefinitionen, Klasse und Schnittstellenbezeichner, für die Frei/Gebucht-API.
ms.openlocfilehash: ec909d449dc9075959fc9c047457577efd52ec3a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790932"
---
# <a name="constants-freebusy-api"></a>Konstanten (Frei/Gebucht-API)

Dieses Thema enthält Konstantendefinitionen, Klasse und Schnittstellenbezeichner, für die Frei/Gebucht-API.
  
## <a name="constants"></a>Konstanten

|**Konstante**|**Definition**|
|:-----|:-----|
|E_NOTIMPL  <br/> | *Wie in der Microsoft Windows Software Development Kit (SDK) Headerdatei winerror.h definiert.*  <br/> |
|E_OUTOFMEMORY  <br/> | *Wie in der Windows SDK Headerdatei winerror.h definiert.*  <br/> |
|S_FALSE  <br/> | *Wie in der Windows SDK Headerdatei winerror.h definiert.*  <br/> |
|S_OK  <br/> | *Wie in der Windows SDK Headerdatei winerror.h definiert.*  <br/> |
   
## <a name="interface-identifiers"></a>Schnittstelle-IDs

Für die folgenden Schnittstellenbezeichner wird vorausgesetzt das DEFINE_GUID-Makro definiert, in der Windows SDK-Header-Datei guiddef.h, dessen Wert den GUID symbolischen Name zugeordnet.
  
{00067064-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IEnumFBBlock, 0x00067064, 0 x 0, 0 x 0, "0xC0", 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 46);
  
{00067066-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IFreeBusyData, 0x00067066, 0 x 0, 0 x 0, "0xC0", 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 46);
  
{00067067-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IFreeBusySupport, 0x00067067, 0 x 0, 0 x 0, "0xC0", 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 0 "," 0 x 46);
  

