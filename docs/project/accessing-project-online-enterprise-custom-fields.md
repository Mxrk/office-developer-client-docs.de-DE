---
title: Zugreifen auf Project Online benutzerdefinierte Enterprise-Felder
manager: soliver
ms.date: 11/08/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 25509631-fa14-49d8-b594-cfacf5355c38
description: 'Project Online ist ein Office 365-Dienst, den geschäftlichen Anforderungen Unternehmen erweitern können. Eine Erweiterung Bereich ist benutzerdefinierte Enterprise-Felder (ECFs). ECFs sind typisierten Wertfelder, die Projekte, Aufgaben und Ressourcen hinzugefügt werden können. In der folgenden Tabelle sind ECFs, die mit Projekten, Ressourcen und Aufgaben zuordnen, und enthält ein Beispiel für einen Wert für eine Instanz dieser ECF:'
ms.openlocfilehash: d6c8f97ffc887b33e5d81af8e463cf10502845dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19796175"
---
# <a name="accessing-project-online-enterprise-custom-fields"></a>Zugreifen auf Project Online benutzerdefinierte Enterprise-Felder

Project Online ist ein Office 365-Dienst, den geschäftlichen Anforderungen Unternehmen erweitern können. Ein Erweiterungsbereich sind die benutzerdefinierten Enterprise-Felder (ECFs). ECFs sind typisierte Wertfelder zu denen Projekte, Aufgaben und Ressourcen hinzugefügt werden können. In der folgenden Tabelle sind ECFs, die mit Projekten, Ressourcen und Aufgaben zugeordnet sind, und enthält ein Beispiel für einen Wert für eine Instanz dieser ECF:
  
|ECF-Name|ECF-Typ|Zuordnung|Beispielwert|
|:-----|:-----|:-----|:-----|
|Begründung  <br/> |TEXT  <br/> |Project  <br/> |Endbenutzer können meine Daten und Gesundheitsdaten mit Ergebnissen, die eine Testversion Integrität und eine individuelle Aktion enthalten aufzuzeichnen. Der Plan ist es, bald besser Integrität zu schaffen.  <br/> |
|Schweregrads  <br/> |TEXT  <br/> |Project  <br/> |Low  <br/> |
|ROI  <br/> |ANZAHL  <br/> |Project  <br/> |2.10  <br/> |
|Gesamtkosten  <br/> |KOSTEN  <br/> |Project  <br/> |$1,031,514  <br/> |
|Starten Sie Team  <br/> |TEXT  <br/> |Ressourcen  <br/> |Ja  <br/> |
|Position-Rolle  <br/> |TEXT  <br/> |Ressourcen  <br/> |Tester  <br/> |
|Kennzeichnungsstatus  <br/> |KENNZEICHNUNG  <br/> |Aufgabe  <br/> |Nein  <br/> |
|Integrität  <br/> |TEXT  <br/> |Aufgabe  <br/> |Nicht angegeben  <br/> |
   
ECFs werden auf der Project Web Application (PWA)-Instanz von Projekt, Ressource oder Vorgang externe definiert. Noch, können sie ein Projekt, Ressource oder Vorgang zugeordnet werden. Dieser Artikel bietet eine grundlegende Aufstellung verwenden ein Beispiel für benutzerdefinierte Felder und liegt der Schwerpunkt auf Abrufen ECF Werte. 
  
Sie können das vollständige Beispiel unter herunterladen https://github.com/OfficeDev/Project-CSOM-Read-Enterprise-CustomFields.
  
Project Online unterstützt darüber hinaus lokale benutzerdefinierte Felder als nur-Lese-Entitäten, die speziell für die bestimmten Projekt, Ressource oder Vorgang. Weitere Informationen über lokale benutzerdefinierte Felder, finden Sie im Beispiel https://github.com/OfficeDev/Project-CSOM-Read-Local-CustomFields\.
  
## <a name="background-materials"></a>Hintergrund Materialien (engl.)

[Entwickeln einer Project Online-Anwendung mit dem clientseitigen Objektmodell](developing-a-project-online-application-using-the-client-side-object-model.md), ein vorherigen Artikel bietet Hintergrundinformationen und die ursprüngliche Ausrichtung für die Entwicklung von Anwendungen mit CSOM. Finden Sie in diesem Artikel finden Sie die folgenden Elemente:
  
- Hintergrundinformationen zu Project, eigenständigen und Cloud-basierte Versionen 
    
- Entwicklungsumgebung (Visual Studio-Editionen und Softwarebibliotheken)
    
- Visual Studio-Projekt-Setup für eine mithilfe der CSOM-Bibliothek
    
- Herstellen einer Verbindung mit Project Online-Dienst
    
## <a name="preliminaries-class-level-declarations"></a>Hinweise (auf Klassenebene Deklarationen)

Die Klasse für diese Anwendung definiert zwei Datenelemente: der Projektkontext und das PwaECF Wörterbuch.
  
Das Projekt Context-Objekt ist Teil der Project-CSOM und verbindet die Anwendung und die PWA-Instanz. Alle Anfragen an den Dienst verwenden den Projektkontext.
  
```cs
private static ProjectContext projContext = 
     new ProjectContext("https://Contoso216.sharepoint.com/sites/pwa");

```

Der Kontext benötigt den Verbindungsendpunkt zum Erstellen einer Instanz in einer Anwendung. Der Verbindungsendpunkt ist die URL der PWA-Instanz. 
  
Das Wörterbuch PwaECF speichert das Projekt, die auf der PWA-Ebene ECFs definiert haben. Das Wörterbuch verwendet die ECF. InternalName als Schlüssel und das benutzerdefiniertes Objekt als Wert. Das Wörterbuch ist in der ListPWACustomFields-Methode aufgefüllt und dann als einen Verweis in der Main-Methode verwendet. 
  
```cs
    //Dictionary of ECFs
        static Dictionary<String, CustomField> pwaECF = new Dictionary<string, CustomField>();

```

## <a name="main-method"></a>Main-Methode

Die Main-Methode verwaltet den Ablauf der Anwendung. Als initialisiert Main mit einer anderen Anwendung, die die Project Online-CSOM verwenden den Projekt-Kontext. 
  
1. Rufen Sie ab und Listen Sie der ECFs in Project Online PWA auf.
    
   Diese Funktionalität ist in der ListPWACustomFields-Methode implementiert.
    
2. Projekte mit benutzerdefinierten Feldern und nicht benutzerdefinierten Felder abrufen.
    
   Beim Abrufen von Projekten mit ECFs muss der abfrageanforderung mit dem Project Online-Dienst die folgenden Elemente enthalten: 
    
   - **IncludeCustomFields** &ndash; Dieses Element fordert den Dienst aus, um eine Auflistung von PublishedProjects zurückzugeben, wobei jedes veröffentlichtes Projekt enthält eine Erweiterung, die benutzerdefinierte Felder unterstützt. Wenn dieses Element angegeben ist, gibt Project Online PublishedProject-Objekte, die keine benutzerdefinierten Felddaten enthalten.
    
   - **IncludeCustomFields.CustomFields** &ndash; dieses Element fordert den Dienst auf die Objekte PublishedProject mit CustomFields Daten auffüllen.
    
   Die folgende Anforderung gibt an, das Projekt-Id und Name, als auch die Objekt-Erweiterung für benutzerdefinierte Felder und die Werte für benutzerdefinierte Felder.
    
   ```cs
        var projBlk = projContext.LoadQuery(
        projContext.Projects.Include(
            p => p.Id, 
            p => p.Name,
            p => p.IncludeCustomFields,
            p => p.IncludeCustomFields.CustomFields
        ));
    
   ```

3. Untersuchen Sie jedes Projekt.
    
   Projektobjekte, die in dieser Anwendung verwendet werden der Typ PublishedProject, da die Werte abgerufen und angezeigt werden. 
    
   Wenn Sie Datenwerte in einem oder mehreren Projekten aktualisieren müssen, würde das Projekt, das Update momentan ausgecheckt werden, und die Anwendung würde ein DraftProject-Objekt verwenden, um die Werte abzurufen und aktualisieren Sie das Projekt.
    
4. Zugreifen auf die ECF-Einträge für ein Projekt
    
   Jede Instanz ECF trennt den Wert des Felds von der restlichen ECF Informationen. Der Wert des Felds wird als Teil der Schlüssel/Wert-Paar gespeichert. Die restlichen Informationen werden in ein benutzerdefiniertes Objekt gespeichert.
    
   Zugreifen auf die Werte in einem Projekt ECF besteht aus zwei Teilen:
    
   - Durchlaufen der Auflistung CustomFields
    
   - Zugreifen auf den entsprechenden Eintrag mit zwei Konstrukte.
    
   Jedes Projekt zugeordneten ECF Einträge an zwei Stellen, eine CustomFields-Auflistung, die aufzählbare wird gespeichert und und die Feldwerte im Rahmen der Schlüssel/Wert-Paare. In der Schlüssel/Wert-Paaren die InternalName ist der Schlüssel und der Wert des Felds ist der Wert. Verwenden eines Wörterbuchs halten und auf die Feldwerte zugreifen. 
    
   Die Eigenschaften ECF als die Feldwerte werden in benutzerdefiniertes-Objekten, ein Objekt pro Projekt gespeichert. Verwenden Sie eine CustomFields-Auflistung, um die einzelnen Projekten zugeordneten ECFs zuzugreifen. 
    
5. Jedes Projekt speichert die zugeordneten ECFs in einer Auflistung, in dem jeder Eintrag ECF besteht aus einem Schlüssel – den internen Namen der ECF – sowie ein Objekt, das den Wert für die ECF enthält. Übertragen der Auflistung in ein Wörterbuch auf einzelne Einträge zugreifen. Die Deklaration folgt.
    
   ```cs
    Dictionary<string, object> projDict = pubProj.IncludeCustomFields.FieldValues;
    
   ```

   Der Wert in einen Wörterbucheintrag entspricht den Datentyp der ECF. Das Objekt für jede ECF ordnet einer der verschiedenen Typen. Die meisten ECFs verwenden einfache Typen, die in den Standardvariablen passen. Das folgende Schemafragment zeigt, dass die minimale Verarbeitung für verschiedene beteiligt ist:
    
   ```cs
    switch (cf.FieldType)
    {
        case CustomFieldType.COST:
            decimal costValue = (decimal)oVal;
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                costValue.ToString("C"));
            break;
        case CustomFieldType.DATE:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.FINISHDATE:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.DURATION:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.FLAG:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
        case CustomFieldType.NUMBER:
            Console.WriteLine("\tFieldType:\t{0}\n\tValue:\t{1}", cf.FieldType, 
                oVal.ToString());
            break;
    
   ```

   Die Nachschlagetabelle mit Textwerten, erfordert jedoch die weitere Verarbeitung weiterleitet. Die Anwendung die entsprechenden Nachschlagetabelle vom Dienst abgerufen, und gibt die Instanz ECF (mit einem oder mehreren Werten) durch Durchlaufen der Nachschlagetabelle. Im folgenden Codefragment zeigt die Verarbeitung von TEXT ECFs, einschließlich derjenigen mit einfachen-Werten und Nachschlagetabellen verwenden: 
    
   ```cs
    case CustomFieldType.TEXT:
        if (!cf.LookupTable.ServerObjectIsNull.HasValue ||
            (cf.LookupTable.ServerObjectIsNull.HasValue && 
            cf.LookupTable.ServerObjectIsNull.Value))
        { //No lookup table
            Console.WriteLine("\tFieldType:\t{0}\n\tText:\t{1}", cf.FieldType, 
                oVal.ToString());
        }
        else
        { //Lookup table
            Console.WriteLine("\tFieldType:\t{0} - using Lookup Table", cf.FieldType);
            String[] entries = (String[])oVal;
            foreach (String entry in entries)
            {
                var luEntry = projContext.LoadQuery(cf.LookupTable.Entries
                    .Where(e => e.InternalName == entry));
                projContext.ExecuteQuery();
                Console.WriteLine("\tLookup Value:\t{0}", luEntry.First().FullValue);  
            }
        }
        break;
    
   ```

   Diese Anwendung gibt einfach die Werte; Es ist jedoch möglich, weitere Bedeutung aus der Daten Werte abzurufen.
    
## <a name="listpwacustomfields"></a>ListPWACustomFields

Die Methode ListPWACustomFields abgerufen und die ECFs Projekten zugeordnet sind. Diese Methode enthält die ECFs registriert auf der PWA-Instanz, die einzelnen Projekte zugeordnet werden kann. Der Einstiegspunkt für den Zugriff auf die ECFs wird das CustomFields-Element des Projektkontexts, wie in der folgenden abfrageanforderung verwendet:
  
```cs
// Project ECFs
    var allECFields = 
            projContext.LoadQuery(projContext.CustomFields.Include(
            qp => qp.InternalName,
            qp => qp.Name
        ));
    projContext.ExecuteQuery();

```

Die Methode wird nicht überprüft, um festzustellen, ob ein Projekt mit einer bestimmten ECF verwendet wird.
  
## <a name="see-also"></a>Siehe auch

- [Project-Entwicklung-Portal](http://dev.office.com/project.aspx)
- [Übersicht: Benutzerdefinierte Enterprise-Felder und Nachschlagetabellen](https://support.office.com/en-us/article/overview-enterprise-custom-fields-and-lookup-tables-f99db553-0b33-4648-93c0-f6a74637d790?ui=en-us&rs=en-us&ad=us)
- [Lokale und benutzerdefinierte Enterprise-Felder](https://msdn.microsoft.com/en-us/library/office/ms447495(v=office.14).aspx)
- [Hinzufügen oder Bearbeiten von benutzerdefinierten Enterprise-Felder in Project Server 2013](https://docs.microsoft.com/en-us/project/add-or-edit-enterprise-custom-fields-in-project-server)
    

