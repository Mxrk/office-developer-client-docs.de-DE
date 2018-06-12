---
title: Office für iOS-Unterstützung für die iOS-Dokumentauswahl
manager: soliver
ms.date: 02/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 802224ef-6eea-4929-824c-507da1c073a5
description: Office für iOS kann mithilfe der Dokumentanbietererweiterung, durch die Office Dateien öffnen kann, die von einem anderen Anbieter gespeichert werden, in die iOS-Dokumentauswahl integriert werden.
ms.openlocfilehash: 101e3cc248f994fe449a74c6c37f788fad8beed5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790890"
---
# <a name="office-for-ios-support-for-the-ios-document-picker"></a><span data-ttu-id="92994-103">Office für iOS-Unterstützung für die iOS-Dokumentauswahl</span><span class="sxs-lookup"><span data-stu-id="92994-103">Office for iOS support for the iOS Document Picker</span></span>

<span data-ttu-id="92994-104">Office für iOS kann mithilfe der Dokumentanbietererweiterung, durch die Office Dateien öffnen kann, die von einem anderen Anbieter gespeichert werden, in die iOS-Dokumentauswahl integriert werden.</span><span class="sxs-lookup"><span data-stu-id="92994-104">Office for iOS integrates with the iOS Document Picker by means of the Document Provider extension, which enables Office to open files stored by another document provider.</span></span>
  
<span data-ttu-id="92994-p101">Versionen von Apple iOS beginnend mit iOS 8.0 umfassen [Unterstützung für die App-Erweiterung](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/index.html#//apple_ref/doc/uid/TP40014214-CH20-SW1). Sie können diese Erweiterungen verwenden, um die Funktionalität Ihrer Anwendung in andere Apps oder Kontexte auf dem Gerät des Benutzers zu erweitern. Um Office für iOS in die iOS-Dokumentauswahl zu integrieren, verwenden Sie die [Dokumentanbietererweiterung](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/FileProvider.html).</span><span class="sxs-lookup"><span data-stu-id="92994-p101">Versions of the Apple iOS starting with iOS 8.0 include [app extension support](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/index.html#//apple_ref/doc/uid/TP40014214-CH20-SW1). You can use these extensions to expand the functionality of your application into other apps or contexts on the user's device. To integrate Office for iOS with the iOS Document Picker, you use the [Document Provider extension](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/FileProvider.html).</span></span>
  
<span data-ttu-id="92994-108">Die Dokumentanbietererweiterung unterstützt vier Vorgänge:</span><span class="sxs-lookup"><span data-stu-id="92994-108">The Document Provider extension supports four operations:</span></span>
  
- <span data-ttu-id="92994-109">Importieren</span><span class="sxs-lookup"><span data-stu-id="92994-109">Import</span></span>
    
- <span data-ttu-id="92994-110">Exportieren</span><span class="sxs-lookup"><span data-stu-id="92994-110">Export</span></span>
    
- <span data-ttu-id="92994-111">Öffnen</span><span class="sxs-lookup"><span data-stu-id="92994-111">Open</span></span>
    
- <span data-ttu-id="92994-112">Verschieben</span><span class="sxs-lookup"><span data-stu-id="92994-112">Move</span></span>
    
<span data-ttu-id="92994-p102">Office für iOS kann in den Vorgang zum Öffnen integriert werden. Wenn Sie eine Dokumentanbietererweiterung erstellen, können Ihre Benutzer die Dokumentauswahl verwenden, um Dokumente direkt in Office zu öffnen und zu bearbeiten, ohne eine Kopie der Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92994-p102">Office for iOS integrates with the open operation. When you create a Document Provider extension, your users can use the Document Picker to open and edit documents directly in Office without creating a duplicate copy of the file.</span></span>
  
## <a name="learn-more-about-app-extensions-and-the-document-picker"></a><span data-ttu-id="92994-115">Weitere Informationen zu App-Erweiterungen und die Dokumentauswahl</span><span class="sxs-lookup"><span data-stu-id="92994-115">Learn more about app extensions and the Document Picker</span></span>
<span data-ttu-id="92994-116"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="92994-116"></span></span>

- [<span data-ttu-id="92994-117">App-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="92994-117">App extensions</span></span>](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/index.html#//apple_ref/doc/uid/TP40014214-CH20-SW1)
    
- [<span data-ttu-id="92994-118">Programmierhandbuch für die Dokumentauswahl</span><span class="sxs-lookup"><span data-stu-id="92994-118">Document Picker Programming Guide</span></span>](https://developer.apple.com/library/prerelease/ios/documentation/FileManagement/Conceptual/DocumentPickerProgrammingGuide/Introduction/Introduction.html)
    
- [<span data-ttu-id="92994-119">Programmierhandbuch für den Dokumentanbieter</span><span class="sxs-lookup"><span data-stu-id="92994-119">Document Provider Programming Guide</span></span>](https://developer.apple.com/library/prerelease/ios/documentation/General/Conceptual/ExtensibilityPG/FileProvider.html)
    
