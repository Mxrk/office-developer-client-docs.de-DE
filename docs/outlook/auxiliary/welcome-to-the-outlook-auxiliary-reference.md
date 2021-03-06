---
title: Willkommen bei der Outlook-Zusatzreferenz
manager: soliver
ms.date: 09/10/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 2e48a625-b3f7-9fd0-253e-fe12a1aca446
description: Die Outlook-Zusatzreferenz enthält konzeptionelle Inhalte und Referenzdokumentation für vier Gruppen von APIs, Codebeispiele und ein verteilbares Installationsprogramm, mit denen Entwickler zur Erweiterung und integrieren in Outlook. APIs in dieser Referenz werden von Outlook für die Erweiterbarkeit, außerhalb der Outlook-Objektmodell verfügbar gemacht.
ms.openlocfilehash: 5f289a1be8fe5d10ddac37394c940f2627415136
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791214"
---
# <a name="welcome-to-the-outlook-auxiliary-reference"></a>Willkommen bei der Outlook-Zusatzreferenz

Die Outlook-Zusatzreferenz enthält konzeptionelle Inhalte und Referenzdokumentation für vier Gruppen von APIs, Codebeispiele und ein verteilbares Installationsprogramm, mit denen Entwickler zur Erweiterung und integrieren in Outlook. APIs in dieser Referenz werden von Outlook für die Erweiterbarkeit, außerhalb der Outlook-Objektmodell verfügbar gemacht. 
  
Wenn Sie gerade erst mit dem Entwickeln von Lösungen für Outlook begonnen haben, finden Sie im Artikel [Auswählen einer API oder Technologie zum Entwickeln von Lösungen für Outlook](../selecting-an-api-or-technology-for-developing-solutions-for-outlook.md) weitere Informationen zu den APIs und Technologien, die am besten zu Ihren Anforderungen passen. 

Bestimmte Informationen über das Outlook-Objektmodell finden Sie unter der [Outlook-VBA-Referenz](http://msdn.microsoft.com/library/75e4ad96-62a2-49d2-bc51-48ceab50634c%28Office.15%29.aspx). 

Spezifische Informationen zu MAPI (Messaging API) von Outlook unterstützt werden finden Sie unter der [Outlook-MAPI-Referenz](http://msdn.microsoft.com/library/3d980b86-7001-4869-9780-121c6bfc7275%28Office.15%29.aspx).

## <a name="conceptual"></a>Konzeptionelle 

Die grundlegende Diskussion umfasst die folgenden Themen:
  
- [Anti-Spam-Einstellungen](about-anti-spam-settings.md)
    
- [Verwalten von Nachricht downloads für POP3-Konten](managing-message-downloads-for-pop3-accounts.md)
    
- [Suchen den Nachrichten-Downloadverlauf für ein POP3-Konto](locating-the-message-download-history-for-a-pop3-account.md)
    
- [Analysieren den Nachrichten-Downloadverlauf für ein POP3-Konto](parsing-the-message-download-history-for-a-pop3-account.md)
    
- [Zur Konfliktbehebung für benutzerdefinierte Elementtypen](about-conflict-resolution-for-custom-item-types.md)
    
- [Informationen zum Zeitpunkt letzten Aktualisierung des eines Offlineadressbuchs](about-the-last-update-time-of-an-offline-address-book.md)
    
- [Zum Registrieren einer neuen Domäne für die automatische Konfiguration](about-registering-a-new-domain-for-automatic-configuration.md)
    
- [Über Besprechungsanfragen als aktualisierte Informationen und vollständige Aktualisierungen](about-meeting-requests-as-informational-updates-and-full-updates.md)
    
- [Informationen zu Basisadressen Kalendern programmgesteuert für Sommerzeit](about-rebasing-calendars-programmatically-for-daylight-saving-time.md) (Es ist auch ein verteilbares Installationsprogramm für Drittanbieter-Kalender Basisadressen Tools, die für frühere Versionen von Outlook auch, ab Outlook 2010 funktioniert. Wenn das Installationsprogramm herunterladen möchten, finden Sie unter [Outlook 2010: Hilfs-Referenz Redistributable Installer und Headerdatei zum Neuzuordnen von Kalendern](http://www.microsoft.com/downloads/details.aspx?FamilyID=77748863-4352-4b99-ae57-1d4ae803983b).)
    
- [Zum Speichern von TZDEFINITION in einen Stream zu einer binären Eigenschaft anvertrauen](about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property.md)

## <a name="reference"></a>Referenz

Der Verweis Inhalt umfasst Folgendes:
  
- Die [APIs von Outlook exportiert](about-apis-exported-by-outlook.md) umfassen Funktionen und Datenstrukturen, die ursprünglich für die interne Verwendung implementiert wurden und jetzt für die öffentliche Verwendung verfügbar gemacht werden. 
    
- Der [Konto-Verwaltungs-API](about-the-account-management-api.md) bietet Zugriff auf Benutzerkontoinformationen und Benachrichtigungen über kontoänderungen. 
    
- Die [Daten der Datenqualität Layer-API](about-the-data-degradation-layer-api.md) unterstützt Clients, die ein Outlook-Element in einem bevorzugten Zeichenformat, anstatt systemeigene Zeichenformat des Objekts zugreifen. 
    
- Die [Frei/Gebucht-API](about-the-free-busy-api.md) bietet Informationen zu bestimmten Benutzerkonten innerhalb eines bestimmten Zeitraums Frei-/Gebucht-Status. 

## <a name="sample-tasks"></a>Beispielaufgaben (engl.)

Die folgenden: Vorgehensweise Beispielaufgaben in der Outlook-Zusatzreferenz
    
- [Bestimmen Sie, ob ein Outlook-Element geändert, jedoch nicht gespeichert (Outlook-Zusatzreferenz) wurde](how-to-determine-if-outlook-item-has-been-modified-but-not-saved.md)
    
- [Analysieren Sie einen Datenstrom aus eine binäre Eigenschaft zum Lesen der TZDEFINITION-Struktur](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
    
- [Analysieren Sie einen Datenstrom aus eine binäre Eigenschaft zum Lesen der TZREG-Struktur](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md)
    
- [Lesen Sie Zeitzone Eigenschaften, ausgehend von einem Termin](how-to-read-time-zone-properties-from-an-appointment.md)
    
- [Gibt an, ob das Bild eines Kontakts in Outlook (Outlook-Zusatzreferenz) anzeigen](https://msdn.microsoft.com/en-us/library/office/gg262879.aspx)
    
- [Verwenden Sie relative Zeit Zugriff auf Frei/Gebucht-Daten](how-to-use-relative-time-to-access-free-busy-data.md)
    
Die Referenz für jede API enthält Konstanten, Typdefinitionen und Schnittstellen, die Entwickler implementieren muss, um die zusätzlichen Funktionen verwenden.
  
> [!NOTE]
> Entwickler müssen diese APIs nur wie in dieser Referenz dokumentiert. Bestimmte Interface-Member und Methodenparameter als Platzhalter heißen, da sie für die interne Verwendung von Outlook reserviert sind und ohne vorherige Ankündigung geändert werden. 
  

