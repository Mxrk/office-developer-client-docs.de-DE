---
title: Abrufen und Festlegen von Eigenschaften mit GetProps und SetProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 309d2b3d-dc71-4222-b293-4bfc467b5429
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 5751dc8b06d40b9f07a39f05868c328d64c27762
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791799"
---
# <a name="getting-and-setting-properties-with-getprops-and-setprops"></a>Abrufen und Festlegen von Eigenschaften mit GetProps und SetProps
 
**Betrifft**: Outlook 
  
Versuchen Sie nach Möglichkeit zum Abfragen und ändern eine Eigenschaft mit den Methoden [IMAPIProp::GetProps](imapiprop-getprops.md) und [IMAPIProp::SetProps](imapiprop-setprops.md) . Es sei denn, die Eigenschaft, die Arbeit mit sehr groß ist, sollten diese Methoden ausreichen. Andere Alternative ist das Lesen oder Schreiben in ein Stream-Objekt mit der [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) -Schnittstelle. Datenströme behandeln sehr große Eigenschaften erfolgreich, aber sie sind eine größere Belastung Ressourcen, da hierfür die COM-Bibliotheken erforderlich sind. Verwenden Sie die **IStream** -Schnittstelle erst nach dem Aufruf von **IMAPIProp::GetProps** oder **IMAPIProp::SetProps** ein Fehler auftritt. 
  

