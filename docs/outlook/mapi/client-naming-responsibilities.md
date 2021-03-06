---
title: Benennen von Client-Aufgaben
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dbb6ba5f-18c8-426f-9f50-ce6f2fd1dc5b
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a97d108b2f36b40e5f8818ea81c138d7384ce9b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791426"
---
# <a name="client-naming-responsibilities"></a>Benennen von Client-Aufgaben

  
  
**Betrifft**: Outlook 
  
Clients müssen einer Namenskonvention für deren Eigenschaften folgen, die von einem Gateway übersetzt werden müssen. Alle Eigenschaften übersetzt werden sollte als benannten Eigenschaften in einer der fünf-Eigenschaft festgelegt, halten Sie sämtliche Eigenschaften erstellt werden:
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
PS_ROUTING_SEARCH_KEY
  
Reagieren auf Eigenschaften, die auf denselben Benutzer beziehen, muss den gleichen Namen angegeben werden. Gateways stützen sich auf diese Benennungskonvention, der eine Adresse mit der richtigen Adresstyp entsprechen kann. Für die Adresse zu analysieren, muss die Zuordnung zwischen Adresse und Adresstyp exakt sein.
  
Benannte Eigenschaften MAPI mit der **MAPINAMEID** -Datenstruktur, gibt an, dass der Name der Eigenschaft, eine Unicode-Zeichenfolge oder eine 32-Bit-Ganzzahl werden kann dargestellt. Weitere Informationen finden Sie unter [MAPINAMEID](mapinameid.md). Ganze Zahl naming wird für Gruppen von Adressen empfohlen, da es eine einfache Möglichkeit zur Unterscheidung zwischen Gruppen von sämtliche Eigenschaften ist, und sie auf einfache Weise als Index für den Benutzer dienen können. Die Alternative zur Verwendung von Ganzzahlen ist eine Zeichenfolge als Namen für alle fünf sämtliche Eigenschaften eines Benutzers zuweisen. Wenn nur ein Benutzer eine Zuordnung erforderlich ist, ist das Zuweisen einer Zeichenfolge zulässig. Wenn mehrere Benutzer vorhanden sind, ist es jedoch besser Ganzzahl naming verwenden. Der Namen sollten, ob es numerische oder Zeichenfolge basierenden sein gespeichert werden, in einer Nachricht-Klasse spezifische Eigenschaft oder in einer Eigenschaft gehört zu einer Eigenschaftensatz, der von der Clientanwendung definiert ist. 
  
> [!NOTE]
> Vermeiden Sie Übersetzung Ganzzahl Namen, Zeichenfolgen, z. B. "route_recipient_1" und "route_recipient_2." Dabei ist nicht erforderlich. 
  
Berücksichtigen Sie zur Veranschaulichung der Funktionsweise dieser Namenskonvention routing-Anwendung, die an jedes Mitglied eines Teams vier Person eine Nachricht sendet. Wenn ein Element die Nachricht empfängt, muss er darauf reagieren, bevor es zusammen mit der kompilierten Antworten auf das nächste Element gesendet werden kann. Die ursprüngliche Nachricht enthält eine Empfängerliste mit einem Eintrag: der erste Mitglied des Teams. Innerhalb der Nachricht eingebettet sind die Gateways sämtliche Eigenschaften für die anderen drei Teammitglieder. Jedes Mitglied hat fünf Kerneigenschaften für Benutzer, die in die Gateway sämtliche Eigenschaftensätze, die eine eindeutige Nummer als Namen einer zugewiesen sind. 
  
Die folgende Tabelle veranschaulicht die Einstellungen für jede Gruppe von Gateway sämtliche Eigenschaften für die drei verbleibenden Teammitglieder, die die Nachricht weitergeleitet wird, wenn das erste Teammitglied er nicht mehr wird, gespeichert.
  
|**Eigenschaftensatz**|**Zweite Team <br/> Member**|**Drittes Team <br/> Member**|**Vierte Team <br/> Member**|
|:-----|:-----|:-----|:-----|
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |Adresse = 0  <br/> |Adresse = 1  <br/> |Adresse = 2  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |Adresstyp = 0  <br/> |Adresstyp = 1  <br/> |Adresstyp = 2  <br/> |
|PS_ROUTING_DISPLAY_NAME  <br/> |Anzeigename = 0  <br/> |Anzeigename = 1  <br/> |Anzeigename = 2  <br/> |
|PS_ROUTING_ENTRYID  <br/> |Eintrags-ID = 0  <br/> |Eintrags-ID = 1  <br/> |Eintrags-ID = 2  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |Suche Schlüssel = 0  <br/> |Suche Schlüssel = 1  <br/> |Suche Schlüssel = 2  <br/> |
   
Clients, die als Verweise auf andere Nachrichteneigenschaften sämtliche Search-Schlüssel verwenden müssen erkennen, dass die anderen Nachrichteneigenschaften werden nicht übersetzt werden, es sei denn, sie in einem der folgenden sämtliche Eigenschaftensätze platziert werden. Wenn eine Nachricht mit nicht zugeordnete Verweise auf zugeordneten Suche Schlüssel an ein Ziel in einer anderen Domäne messaging gesendet wird, sind die Verweise ungültig. Um diese zu anderen Eigenschaften, mit der Suche Keys synchronisiert bleiben aktivieren, können Sie diese Zeichenfolgennamen im Eigenschaftensatz PS_ROUTING_SEARCH_KEY zuordnen, die die Namen von Core sämtliche Eigenschaften nicht stören. Angenommen Sie, dass ein Client muss eine Eigenschaft zu übertragen, die den Search-Schlüssel für die letzte Person eine lange Routingliste enthält. Der Client kann eine benannte Eigenschaft im Eigenschaftensatz PS_ROUTING_SEARCH_KEY namens "Last_search_key." erstellen. Da sie in einem Eigenschaftensatz sämtliche-gespeichert ist, wird zusammen mit dem Rest der Gateway sämtliche Eigenschaften die Eigenschaft "Last_search_key" übersetzt.
  

