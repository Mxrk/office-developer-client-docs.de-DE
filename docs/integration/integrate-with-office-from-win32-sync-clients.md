---
title: Integration in Office von Win32-Synchronisierungsclients aus
manager: soliver
ms.date: 07/29/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 348555d3-3cd4-4e4a-b5ad-436571c25251
description: Integrieren Sie Ihre Drittanbieter-Win32-Synchronisierungsclients mit Excel Mobile-, PowerPoint Mobile- und Word Mobile-Office-Anwendungen.
ms.openlocfilehash: 9f520ad36583a9aa7cd73638fe92158f70d13daf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790858"
---
# <a name="integrate-with-office-from-win32-sync-clients"></a><span data-ttu-id="1e600-103">Integration in Office von Win32-Synchronisierungsclients aus</span><span class="sxs-lookup"><span data-stu-id="1e600-103">Integrate with Office from Win32 sync clients</span></span>

<span data-ttu-id="1e600-104">Integrieren Sie Ihre Drittanbieter-Win32-Synchronisierungsclients mit Excel Mobile-, PowerPoint Mobile- und Word Mobile-Office-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1e600-104">Integrate your third-party Win32 sync clients with Excel Mobile, PowerPoint Mobile, and Word Mobile Office applications.</span></span> 
  
<span data-ttu-id="1e600-p101">Sie können Ihre universelle Windows-App mit Excel Mobile-, PowerPoint Mobile- und Word Mobile-Clients integrieren, indem Sie sie als Synchronisierungsstammanbieter registrieren. In diesem Artikel werden die bewährten Methoden beschrieben, um sicherzustellen, dass Ihre Win32-Synchronisierungsclients problemlos mit Office-Anwendungen zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1e600-p101">You can integrate your Windows universal app with Excel Mobile, PowerPoint Mobile, and Word Mobile clients by registering as a sync root provider. This article describes the best practices to apply to ensure that your Win32 sync clients work well with Office applications.</span></span>
  
<span data-ttu-id="1e600-107">Für diese Integration muss der Win32-Synchronisierungsclient über ein Synchronisierungsmodul verfügen.</span><span class="sxs-lookup"><span data-stu-id="1e600-107">This integration requires that your Win32 sync client has a sync engine.</span></span>
  
## <a name="register-as-a-sync-root-provider"></a><span data-ttu-id="1e600-108">Registrieren als Synchronisierungsstammanbieter</span><span class="sxs-lookup"><span data-stu-id="1e600-108">Register as a sync root provider</span></span>

<span data-ttu-id="1e600-p102">Wenn Ihr Synchronisierungsclient nicht als Synchronisierungsstammanbieter registriert ist, behandelt Office Dateien im Synchronisierungsordner wie normale lokale Dateien. Dies bedeutet, dass Office Benutzern Optionen wie "Zu OneDrive verschieben" anbietet, wenn sie versuchen, das Dokument freizugeben. Um dies für Dateien zu vermeiden, die Sie synchronisieren, müssen Sie die Registrierung als Synchronisierungsstammanbieter ausführen. Informationen über das Registrieren finden Sie unter [Integrieren eines Cloud-Speicheranbieters](https://msdn.microsoft.com/en-us/library/windows/desktop/dn889934%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e600-p102">Unless your sync client is registered as a sync root provider, Office will treat files in your sync folder the way that it treats regular local files. This means that Office will provide "move to OneDrive" options for users when they attempt to share the document. To avoid this for files you sync, you must register as a sync root provider. For information about how to register, see [Integrate a Cloud Storage Provider](https://msdn.microsoft.com/en-us/library/windows/desktop/dn889934%28v=vs.85%29.aspx).</span></span>
  
## <a name="integrate-your-app-into-the-root-node-of-the-navigation-pane"></a><span data-ttu-id="1e600-113">Integrieren der App in den Stammknoten des Navigationsbereichs</span><span class="sxs-lookup"><span data-stu-id="1e600-113">Integrate your app into the root node of the navigation pane</span></span>

<span data-ttu-id="1e600-p103">Damit Ihr Win32-Synchronisierungsclient im Datei-Explorer und der Windows-Dateiauswahl als Stammknoten im Navigationsbereich angezeigt wird, müssen Sie Ihre App in die Stammebene integrieren. Weitere Informationen dazu finden Sie unter [Integrieren eines Cloud-Speicheranbieters](https://msdn.microsoft.com/en-us/library/windows/desktop/dn889934%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e600-p103">In order for your Win32 sync client to show up as a root node in the navigation pane in the File Explorer and Windows file picker, you need to integrate your app into the root level. For information about how to do this, see [Integrate a Cloud Storage Provider](https://msdn.microsoft.com/en-us/library/windows/desktop/dn889934%28v=vs.85%29.aspx).</span></span> 
  
## <a name="add-your-sync-folder-as-a-document-library-optional"></a><span data-ttu-id="1e600-116">Hinzufügen des Synchronisierungsordners als Dokumentbibliothek (optional)</span><span class="sxs-lookup"><span data-stu-id="1e600-116">Add your sync folder as a document library (optional)</span></span>

<span data-ttu-id="1e600-p104">In Office können Benutzer mit einer einzelnen Aktion Dokumente in ihren Dokumentbibliotheken erstellen. Um Ihren Synchronisierungsspeicherort der Dokumentbibliothek hinzuzufügen, verwenden Sie die [SHAddFolderPathToLibrary-Funktion](https://msdn.microsoft.com/en-us/library/windows/desktop/dd378432%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e600-p104">In Office, users can create documents in their document libraries with a single action. To add your sync location to the document library, use the [SHAddFolderPathToLibrary function](https://msdn.microsoft.com/en-us/library/windows/desktop/dd378432%28v=vs.85%29.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1e600-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e600-119">See also</span></span>
<span data-ttu-id="1e600-120"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="1e600-120"></span></span>

- [<span data-ttu-id="1e600-121">Integration in Office</span><span class="sxs-lookup"><span data-stu-id="1e600-121">Integrate with Office</span></span>](integrate-with-office.md)
    
- [<span data-ttu-id="1e600-122">Integration in Office von universellen Windows-Apps aus</span><span class="sxs-lookup"><span data-stu-id="1e600-122">Integrate with Office from Windows universal apps</span></span>](integrate-with-office-from-windows-universal-apps.md)
    
