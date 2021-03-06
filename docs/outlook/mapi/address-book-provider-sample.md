---
title: Address Book Anbieter Sample
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2ccf1643-5604-4fee-92cc-3d6af00e7f98
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: c32017598407760d5dbbb01ee6c28267bbffd152
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791262"
---
# <a name="address-book-provider-sample"></a>Address Book Anbieter Sample

  
  
**Betrifft**: Outlook 
  
In diesem Beispiel unterstützt einen einzelnen schreibgeschützten Container für Anzeigenamen und e-Mail-Adressen, die aus einer flachen Binärdatei gelesen werden. Im Beispiel werden einmal-Vorlagen und alle Konfigurationsoptionen, mit Ausnahme der Profil-Assistent unterstützt.
  
Sie können dieses Beispiel aus [Outlook Messaging-API (MAPI)-Codebeispiele](http://go.microsoft.com/fwlink/?LinkId=129740
)herunterladen.
  
|||
|:-----|:-----|
|Ausführbare Datei:  <br/> |SABP32.dll  <br/> |
| Code Quellverzeichnis:  <br/> |SampleAddressBookProvider\SABP  <br/> |
|Sprache:  <br/> |C++  <br/> |
|Plattformen:  <br/> |Microsoft Visual Studio 2008 zum Kompilieren für Windows Vista, Windows Server 2008, Windows XP SP2 und Windows Server 2003 SP1  <br/> |
   
## <a name="supported-features"></a>Unterstützte Features

In diesem Beispiel werden die folgenden Features unterstützt:
  
- Tabelle Einschränkungen. Im Beispiel wird die präfixübereinstimmung und mehrdeutiger Name Resolution implementiert. Die vollständige MAPI-Einschränkung Sprache wird nicht implementiert, und Einschränkungen sind nur für den Anzeigenamen unterstützt.
    
- Eine Tabelle, für Benutzer messaging Details anzeigen. 
    
- Einmal-Adressen.
    
- Ein Dialogfeld Erweiterte Suche.
    
- Ein [IMAPIStatus: IMAPIProp](imapistatusimapiprop.md) Schnittstelle. Diese Schnittstelle ist teilweise unterstützt. seine **IMAPIProp** Methoden werden an die Schnittstelle **IPropData** delegiert. Weitere Informationen finden Sie unter der [IPropData: IMAPIProp](ipropdataimapiprop.md) Schnittstelle. 
    
- Interaktive und programmgesteuerte Konfiguration.
    
## <a name="unsupported-features"></a>Nicht unterstützte Features

In diesem Beispiel wird die folgenden Features nicht unterstützt:
  
- Sortieren.
    
- Verteilerlisten.
    
- Erstellen, löschen und Ändern von Einträgen.
    
- Eigenschaften mit mehreren Werten.
    
- Benannte Eigenschaften.
    
- Unterscheidung zwischen vor- und Nachnamen Namen im Anzeigenamen.
    
 **So installieren Sie die Beispiel-Adressbuchanbieter**
  
1. Wenn die Beispiel-Adressbuchanbieter herunterladen möchten, finden Sie unter [Herunterladen der MAPI-Beispiele für Outlook](downloading-the-outlook-mapi-samples.md).
    
2. Suchen Sie den Ordner, in dem Sie die MAPI-Beispiele für Outlook gespeichert. Mit der rechten Maustaste die **OutlookMAPISamples -\<Versionsnummer\> ** zip-Ordner, und klicken Sie auf **Alle extrahieren**.
    
3. Klicken Sie auf **Durchsuchen**, markieren Sie den Speicherort, in dem Sie das Beispiel zu speichern möchten, und klicken Sie auf **extrahieren**.
    
4. Führen Sie Visual Studio 2008.
    
5. Klicken Sie in Visual Studio 2008 auf **Datei**, klicken Sie auf **Öffnen**, und klicken Sie dann auf **Projekt/Projektmappe**.
    
6. Navigieren Sie zum Speicherort, in dem Sie das Beispiel gespeichert haben, klicken Sie auf **SABP.vcproj**und klicken Sie dann auf **Öffnen**.
    
7. On the **Build** menu, click **Build Solution**.
    
8. Klicken Sie im Dialogfeld **Datei speichern unter** auf **Speichern**.
    
9. In den Ordner, in dem Sie das Beispiel gespeichert haben, mit der rechten Maustaste in der Datei **Install.bat aus** , und klicken Sie auf **als Administrator ausführen**.
    
10. Klicken Sie im Dialogfeld **Benutzerkontensteuerung** auf **Weiter**.
    
    > [!NOTE]
    > **Install.bat** kopiert die DLL-Datei in den standardmäßigen Microsoft Office-Installationsordner C:\Program Files\Microsoft Office\Office12\. Wenn Sie Office-Produkte an einem anderen Speicherort installiert haben, mit der rechten Maustaste **Install.bat aus** , und klicken Sie auf **Bearbeiten**. Die Datei wird im Editor geöffnet. Ersetzen Sie den Standardpfad für die Installation durch den Installationspfad auf Ihrem Computer verwendet. 
  

