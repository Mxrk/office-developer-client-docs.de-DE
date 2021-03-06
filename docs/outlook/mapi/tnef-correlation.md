---
title: TNEF Korrelation
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93d1716d-a0be-45aa-85d2-6c9be65f5fd2
description: 'Zuletzt geändert: 12 März 2013'
ms.openlocfilehash: b8b30dcc2fcf0c8e75004e36b6fd9f4f4583e304
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795737"
---
# <a name="tnef-correlation"></a>TNEF Korrelation

 
  
**Betrifft**: Outlook 
  
Einige Messagingsysteme führen Sie eine Überprüfung der Korrelation für jeden Transport-Neutral Encapsulation Format (TNEF) Stream, um sicherzustellen, dass der TNEF-Stream tatsächlich zu dieser Nachricht gehört eine eingehende Nachricht zugeordnet ist. Dieser Schritt umfasst das dem Wert der ein Feld in der Kopfzeile der eingehenden Nachricht mit einer Kopie des Werts in eine Eigenschaft in der TNEF-Stream gespeichert. Werte, die vermutlich eindeutig für jede Nachricht, wie etwa Nachricht-ID-Nummern sind werden in der Regel für diese verwendet. Die Transport oder das Gateway, die den TNEF-Stream erstellt ist verantwortlich für einen entsprechenden Wert aus der Nachrichtenkopf auswählen und platziert eine Kopie in einer entsprechenden Eigenschaft vor die ausgehende Nachricht Eigenschaften in den Stream TNEF-Codierung. Gateways oder Transporten, die die Nachricht empfangen können dann diese Eigenschaft aus dem TNEF-Stream extrahieren und stellen Sie sicher, dass der Wert den Wert des entsprechenden Felds Kopfzeile der eingehenden Nachricht übereinstimmt.
  
Wenn die Werte nicht übereinstimmen, sollte das Gateway oder Transport die TNEF-Stream und Prozess nur die systemeigene Nachrichtenumschlag verwerfen. Kontrollen sind ratsam, da nicht-MAPI-basierten e-Mail-Clients können eine Datei anfügen, die einen TNEF-Stream aus einer alten Nachricht an eine Weiterleitung oder sogar eine unabhängige Nachricht enthält. Wenn nicht aktiviert, möglicherweise eine solche Fehlermeldung den Verlust des Nachrichtentexts.
  
Der Wert des Felds Kopfzeile ausgewählt muss an die Nachricht eindeutig sein. Keine festen Kopfzeilenfeld für alle Messagingsysteme vorhanden ist, da verschiedene Messagingsystemen unterschiedliche Kopf-Felder verwendet werden, aber in der Regel das messaging-System weist einen eindeutigen Bezeichner der Nachricht, die für diesen Zweck geeignet ist. Beispielsweise verwenden SMTP-Systeme in der Regel die Kopfzeile MessageID während x. 400-Systeme in der Regel das IM_THIS_IPM-Attribut verwenden.
  

