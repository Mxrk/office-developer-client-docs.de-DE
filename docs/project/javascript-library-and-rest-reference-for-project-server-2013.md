---
title: JavaScript-Bibliothek und REST-Referenz für Project Server
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 67b47b8b-d34b-4fad-af49-0c258c345ad2
description: Verweisen die JavaScript-Bibliothek und REST für Project Server 2013 enthält Informationen über das JavaScript-Objektmodell und der REST-Schnittstelle, mit denen Sie Zugriff auf Project Server-Funktionen. Sie können diese APIs zum Entwickeln browserübergreifende Web apps, Project Professional 2013-add-ins und apps für nicht-Windows-Geräte, die Zugriff auf Project Server 2013 und Project Online verwenden.
ms.openlocfilehash: f834ffdc80de28eceb2d7ab9b30c1444b0478bd8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19796190"
---
# <a name="javascript-library-and-rest-reference-for-project-server"></a>JavaScript-Bibliothek und REST-Referenz für Project Server

Verweisen die JavaScript-Bibliothek und REST für Project Server 2013 enthält Informationen über das JavaScript-Objektmodell und der REST-Schnittstelle, mit denen Sie Zugriff auf Project Server-Funktionen. Sie können diese APIs zum Entwickeln browserübergreifende Web apps, Project Professional 2013-add-ins und apps für nicht-Windows-Geräte, die Zugriff auf Project Server 2013 und Project Online verwenden.
  
> [!NOTE]
> Richten die JavaScript-Objektmodell und REST-Schnittstelle mit dem Project Server mithilfe der clientseitigen Objektmodell (CSOM). Sie bieten entsprechenden Funktionalität auf den **Microsoft.ProjectServer.Client** -Namespace in das CSOM. 
  
Sie können Project Server-Funktionen zugreifen, über das JavaScript-Objektmodell, die im [PS](http://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx) -Namespace in definiert ist die `%ProgramFiles%\Common Files\Microsoft Shared\Web Server Extensions\15\TEMPLATE\LAYOUTS\PS.js` Datei. Das Objekt [ProjectContext](http://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx) im [PS](http://msdn.microsoft.com/library/e3156167-a4fd-1bf6-8d1c-e180de1844ed%28Office.15%29.aspx) -Namespace ist der Einstiegspunkt für das JavaScript-Objektmodell. 
  
> [!NOTE]
> Das JavaScript-Objektmodell zu durchsuchen und das Debuggen zu unterstützen, können Sie die PS.debug.js-Datei im gleichen Verzeichnis befindet. Um Hilfe bei der Entwicklung auf einem Remotecomputer, umfasst das [Project 2013-SDK herunterladen](https://www.microsoft.com/en-us/download/details.aspx?id=30435) .NET Framework-Assemblys für das CSOM und die PS.js und PS.debug.js-Dateien. 
  
Sie können auch über die REST-Schnittstelle von Project Server-Funktionen zugreifen. Der Einstiegspunkt in der REST-Schnittstelle ist die **ProjectServer** -Ressource, die Sie mithilfe von zugreifen die `http://ServerName/pwaName/_api/ProjectServer` Endpunkt-URI. Beispielsweise die folgende Abfrage dient zum Abrufen der Zuordnungen in das angegebene Projekt (ersetzen Sie _ServerName_ und _PwaName_und die GUID ein Projekts entsprechend ändern).
  
`http://ServerName/pwaName/_api/ProjectServer/Projects('263fc8d7-427c-e111-92fc-00155d3ba208')/Assignments`

Die **ProjectServer** -Ressource wird in [ProjectServer-Ressourcen in der REST-Schnittstelle](http://msdn.microsoft.com/library/a490b675-a845-ee94-3877-b99ada9bf2b0%28Office.15%29.aspx#bk_ProjectServerResources)beschrieben. Andere REST-Ressourcen werden in der Dokumentation für die entsprechenden JavaScript-Objekte und Member in dieser Referenz beschrieben. Weitere Informationen zur Verwendung von REST finden Sie unter [Client-seitigen Objektmodell (CSOM) für Project Server](client-side-object-model-csom-for-project-2013.md) und [Programmierung mithilfe von SharePoint 2013 REST-Dienst](http://msdn.microsoft.com/en-us/library/fp142385%28office.15%29.aspx).
  
## <a name="javascript-library-and-rest-reference-for-project-server"></a>JavaScript-Bibliothek und REST-Referenz für Project Server
<a name="pj15_JavaScriptAPIReference_PS"> </a>

- [PS.js JavaScript-Bibliothek und REST-Referenz](http://msdn.microsoft.com/library/5a140021-380a-d9e0-e36d-106df85f56d6%28Office.15%29.aspx) Enthält Informationen über das JavaScript-Objektmodell und der REST-Schnittstelle für Project Server 2013. 
    
## <a name="see-also"></a>Siehe auch
<a name="bk_addresources"> </a>

- [Project 2013-Entwicklerdokumentation](project-2013-developer-documentation.md)   
- [Client-seitigen Objektmodell (CSOM) für Project Server](client-side-object-model-csom-for-project-2013.md)   
- [Erste Schritte mit der JavaScript-Objektmodell](getting-started-with-the-project-server-2013-javascript-object-model.md)  
- [Arbeiten Sie mit Projekten mithilfe des JavaScript-Objektmodells](create-retrieve-update-delete-projects-using-project-server-javascript.md)
    

