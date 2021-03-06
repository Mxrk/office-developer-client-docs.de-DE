---
title: Beispiel für einen Nachrichtenspeicher
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f1e4077b-7a95-440d-a326-a8dc9cdab4fe
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: b3c907b0a53a41a52516b23ffb1cf7400d887d89
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793260"
---
# <a name="message-store-provider-sample"></a>Beispiel für einen Nachrichtenspeicher

  
  
**Betrifft**: Outlook 
  
Der umbrochen PST Store Beispielanbieter verwendet einen Anbieter für Persönliche Ordner-Datei (PST) als Back-End zum Speichern von Daten. Der gepackten PST-Speicheranbieter sollten zusammen mit der API für die Replikation verwendet werden. 
  
Replikation der API können Sie Elemente in einem Microsoft Outlook-PST-Speicher aus einem Back-End-Daten-Repository repliziert werden. Sie verwenden die Replikation-API zum Replizieren von Daten in einer dedizierten PST-Speicher und verfolgen an den Synchronisierungsstatus. Weitere Informationen finden Sie unter [Informationen zu Replikation API](about-the-replication-api.md).
  
Die meisten Funktionen in der umbrochen PST Store Beispielanbieter übergeben ihre Argumente direkt an dem zugrunde liegenden PST-Anbieter. Bestimmte Funktionen erfordern besondere Implementierung und werden in den folgenden Themen beschrieben.
  
|||
|:-----|:-----|
|Ausführbare Datei:  <br/> |WrpPST32.dll  <br/> |
|Code Quellverzeichnis:  <br/> |SampleWrappedPSTStoreProvider\WrapPST  <br/> |
|Sprache:  <br/> |C++  <br/> |
|Plattformen:  <br/> |Microsoft Visual Studio 2008 zum Kompilieren für Windows Vista, Windows Server 2008, Windows XP SP2 und Windows Server 2003 SP1  <br/> |
   
## <a name="supported-features"></a>Unterstützte Features

In diesem Beispiel unterstützt Microsoft Outlook 2010 64-Bit- und wurde für Outlook 2013 jetzt überarbeitet. Finden Sie unter den folgenden Themen Weitere Informationen:
  
- [Über die API-Replikation](about-the-replication-api.md)
    
- [Initialisieren einen Anbieter für umbrochenen PST anmelden](initializing-a-wrapped-pst-store-provider.md)
    
- [Anmelden bei einem Anbieter gepackten PST-Datei](logging-on-to-a-wrapped-pst-store-provider.md)
    
- [Verwenden eines Anbieters gepackten PST-Speichers](using-a-wrapped-pst-store-provider.md)
    
- [Herunterfahren von einem Anbieter gepackten PST-Datei](shutting-down-a-wrapped-pst-store-provider.md)
    
 **So installieren Sie die umfließendem PST Store Beispielanbieter**
  
1. Zum Beispiel umgebrochen PST-Anbieter finden Sie unter [Herunterladen der MAPI-Beispiele für Outlook](downloading-the-outlook-mapi-samples.md).
    
2. Suchen Sie den Ordner, in dem Sie die MAPI-Beispiele für Outlook gespeichert. Mit der rechten Maustaste die **OutlookMAPISamples -\<Versionsnummer\> ** zip-Ordner, und klicken Sie dann auf **Alle extrahieren**.
    
3. Klicken Sie auf **Durchsuchen**, markieren Sie den Speicherort, in dem Sie das Beispiel zu speichern möchten, und klicken Sie dann auf **extrahieren**.
    
4. Führen Sie Microsoft Visual Studio 2008.
    
5. Klicken Sie in Microsoft Visual Studio 2008 auf **Datei**, klicken Sie auf **Öffnen**, und klicken Sie dann auf **Projekt/Projektmappe**.
    
6. Navigieren Sie zum Speicherort, in dem Sie das Beispiel gespeichert haben, klicken Sie auf **WrapPST.vcproj**und klicken Sie dann auf **Öffnen**.
    
7. On the **Build** menu, click **Build Solution**.
    
8. Klicken Sie im Dialogfeld **Datei speichern unter** auf **Speichern**.
    
9. In den Ordner, in dem Sie das Beispiel gespeichert haben, mit der rechten Maustaste in der Datei **Install.bat aus** , und klicken Sie dann auf **als Administrator ausführen**.
    
10. Klicken Sie im Dialogfeld **Benutzerkontensteuerung** auf **Weiter**.
    

