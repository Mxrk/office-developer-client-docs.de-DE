---
title: Senden von Nachrichten Nachrichtenspeicher Anbieter Aufgaben
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: acbfd3ae-bfdc-4103-bed2-6bcf7b9c448c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 8bfa5709dede4a9501d261e0f495acbc0894b470
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795496"
---
# <a name="sending-messages-message-store-provider-tasks"></a><span data-ttu-id="66f03-103">Senden von Nachrichten: Nachrichtenspeicher Anbieter Aufgaben</span><span class="sxs-lookup"><span data-stu-id="66f03-103">Sending Messages: Message Store Provider Tasks</span></span>

<span data-ttu-id="66f03-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="66f03-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="66f03-p101">A message store provider gets involved with the message sending process when a client calls the message's [IMessage::SubmitMessage](imessage-submitmessage.md) method. If multiple messages are to be sent, the message store must send them in the same order that the client used for its **SubmitMessage** calls.</span><span class="sxs-lookup"><span data-stu-id="66f03-p101">A message store provider gets involved with the message sending process when a client calls the message's [IMessage::SubmitMessage](imessage-submitmessage.md) method. If multiple messages are to be sent, the message store must send them in the same order that the client used for its **SubmitMessage** calls.</span></span> 
  
<span data-ttu-id="66f03-p102">Der Nachricht Informationsdienst bestimmt, ob er die MAPI-Warteschlange umfassen. Wenn die Nachricht Informationsdienst nicht eng verkn�pft ist, die Nachricht muss Vorverarbeitung, oder den eng gekoppelten Speicher und Transport k�nnen nicht bearbeitet werden alle Empf�nger, die MAPI-Warteschlange beteiligt sein muss.</span><span class="sxs-lookup"><span data-stu-id="66f03-p102">The message store provider determines whether or not to involve the MAPI spooler. If the message store provider is not tightly coupled, the message requires preprocessing, or the tightly coupled store and transport cannot handle all of the recipients, the MAPI spooler must be involved.</span></span> 
  
<span data-ttu-id="66f03-109">Das folgende Verfahren beschreibt die von einem Nachrichtenanbieter zum Senden einer Nachricht erforderlichen Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="66f03-109">The following procedure describes the tasks required of a message store provider for sending a message.</span></span> 
  
<span data-ttu-id="66f03-110">**In der IMessage::SubmitMessage die Nachricht Speicheranbieter**:</span><span class="sxs-lookup"><span data-stu-id="66f03-110">**In IMessage::SubmitMessage, the message store provider**:</span></span>
  
1. <span data-ttu-id="66f03-111">[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) aufgerufen, wenn die Nachricht das MSGFLAG_RESEND-Flag, das in der **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))-Eigenschaft festgelegt wurde und Fehlermeldungen an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="66f03-111">Calls [IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) if the message has the MSGFLAG_RESEND flag set in its **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property and returns any errors to the client.</span></span> <span data-ttu-id="66f03-112">**PrepareSubmit** überprüft die **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))-Eigenschaft der einzelnen Empfänger in der Liste der Empfänger der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="66f03-112">**PrepareSubmit** checks the **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) property of each recipient in the message's recipient list.</span></span>
    
   - <span data-ttu-id="66f03-113">Wenn das Flag MAPI_SUBMITTED festgelegt ist, gibt an, dass der Empfänger die ursprüngliche Nachricht nicht erhalten haben, **PrepareSubmit** löscht das Flag und die **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))-Eigenschaft auf TRUE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="66f03-113">If the MAPI_SUBMITTED flag is set, indicating that the recipient did not receive the original message, **PrepareSubmit** clears the flag and sets the **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property to TRUE.</span></span> 
    
   - <span data-ttu-id="66f03-114">Wenn das Flag MAPI_SUBMITTED nicht festgelegt ist, der angibt, dass der Empf�nger der urspr�nglichen Nachricht erhalten hat, �ndert die Eigenschaft **PR_RECIPIENT_TYPE** in MAPI_P1 **PrepareSubmit** und die **PR_RESPONSIBILITY** -Eigenschaft auf TRUE festgelegt und etwaige Fehler generierte **PrepareSubmit** an den Client zur�ckgegeben.</span><span class="sxs-lookup"><span data-stu-id="66f03-114">If the MAPI_SUBMITTED flag is not set, indicating that the recipient did receive the original messsage, **PrepareSubmit** changes the **PR_RECIPIENT_TYPE** property to MAPI_P1 and sets the **PR_RESPONSIBILITY** property to TRUE and returns any error generated by **PrepareSubmit** to the client.</span></span> 
    
2. <span data-ttu-id="66f03-115">Das Flag MSGFLAG_SUBMIT festgelegt in der Nachricht **PR_MESSAGE_FLAGS** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="66f03-115">Sets the MSGFLAG_SUBMIT flag in the message's **PR_MESSAGE_FLAGS** property.</span></span> 
    
3. <span data-ttu-id="66f03-116">Stellt sicher, dass eine Spalte f�r **PR_RESPONSIBILITY** in der Tabelle Empf�nger und wird auf false fest, um anzugeben, dass kein Transport noch angenommenen Verantwortung f�r die �bermittlung der Nachricht wurde.</span><span class="sxs-lookup"><span data-stu-id="66f03-116">Makes sure that there is a column for **PR_RESPONSIBILITY** in the recipient table and sets it to FALSE to indicate that no transport has of yet assumed responsibility for transmitting the message.</span></span> 
    
4. <span data-ttu-id="66f03-117">Legt das Datum und die Uhrzeit der Aufnahme in der Eigenschaft **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)).</span><span class="sxs-lookup"><span data-stu-id="66f03-117">Sets the date and time of origination in the **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) property.</span></span>
    
5. <span data-ttu-id="66f03-118">Calls [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) to:</span><span class="sxs-lookup"><span data-stu-id="66f03-118">Calls [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md) to:</span></span> 
    
   - <span data-ttu-id="66f03-119">Erweitern Sie alle pers�nlichen Verteilerlisten und benutzerdefinierte Empf�nger, und Ersetzen Sie alle ge�nderten Anzeigenamen durch ihren Originalnamen.</span><span class="sxs-lookup"><span data-stu-id="66f03-119">Expand all personal distribution lists and custom recipients and replace all changed display names with their original names.</span></span>
   - <span data-ttu-id="66f03-120">Entfernen von Duplikaten.</span><span class="sxs-lookup"><span data-stu-id="66f03-120">Remove duplicate names.</span></span>
   - <span data-ttu-id="66f03-121">Erforderliche vorverarbeitung suchen Sie, und wenn der vorverarbeitung erforderlich ist, legen Sie das Kennzeichen NEEDS_PREPROCESSING und der **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md))-Eigenschaft, einer Eigenschaft, die für die MAPI reserviert.</span><span class="sxs-lookup"><span data-stu-id="66f03-121">Check for any required preprocessing, and if preprocessing is required, set the NEEDS_PREPROCESSING flag and the **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) property, a property reserved for MAPI.</span></span> 
   - <span data-ttu-id="66f03-122">Legen Sie das Flag NEEDS_SPOOLER, wenn der Nachrichtenspeicher eng mit einer Transport verkn�pft ist und nicht behandelt alle Empf�nger werden kann.</span><span class="sxs-lookup"><span data-stu-id="66f03-122">Set the NEEDS_SPOOLER flag if the message store is tightly coupled with a transport and it cannot handle all of the recipients.</span></span> 
    
6. <span data-ttu-id="66f03-123">F�hrt die folgenden Aufgaben aus, wenn der Nachrichtenkennzeichnung NEEDS_PREPROCESSING festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="66f03-123">Performs the following tasks if the NEEDS_PREPROCESSING message flag is set:</span></span>
    
   - <span data-ttu-id="66f03-124">Versetzt die Nachricht in der ausgehenden Warteschlange mit dem SUBMITFLAG_PREPROCESS Bit in der Eigenschaft **PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="66f03-124">Puts the message in the outgoing queue with the SUBMITFLAG_PREPROCESS bit set in the **PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) property.</span></span>
   - <span data-ttu-id="66f03-125">Benachrichtigt die MAPI-Warteschlange, die die Warteschlange ge�ndert wurde.</span><span class="sxs-lookup"><span data-stu-id="66f03-125">Notifies the MAPI spooler that the queue has changed.</span></span>
   - <span data-ttu-id="66f03-126">Gibt die Steuerung an den Client, und Nachrichtenfluss wird in die Warteschlange MAPI fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="66f03-126">Returns control to the client, and message flow continues in the MAPI spooler.</span></span> 
   - <span data-ttu-id="66f03-127">Die MAPI-Warteschlange f�hrt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="66f03-127">The MAPI spooler performs the following tasks:</span></span>
     - <span data-ttu-id="66f03-128">Sperrt die Nachricht durch Aufrufen von IMsgStore::SetLockState.</span><span class="sxs-lookup"><span data-stu-id="66f03-128">Locks the message by calling IMsgStore::SetLockState.</span></span> 
     - <span data-ttu-id="66f03-129">Führt die erforderlichen vorverarbeitung durch Aufrufen von alle vorverarbeitenden Funktionen in der Reihenfolge der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="66f03-129">Performs the needed preprocessing by calling all of the preprocessing functions in the order of registration.</span></span> <span data-ttu-id="66f03-130">Transportanbieter aufrufen IMAPISupport::RegisterPreprocessor vorverarbeitenden Funktionen registrieren.</span><span class="sxs-lookup"><span data-stu-id="66f03-130">Transport providers call IMAPISupport::RegisterPreprocessor to register preprocessing functions.</span></span> 
     - <span data-ttu-id="66f03-131">Ruft IMessage::SubmitMessage auf der geöffneten Nachricht der Nachrichtenspeicher an, dass der vorverarbeitung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="66f03-131">Calls IMessage::SubmitMessage on the open message to indicate to the message store that preprocessing is complete.</span></span>

<br/>

<span data-ttu-id="66f03-132">Die folgenden beiden Schritte auftreten im Clientprozess, wenn es wurde keine vorverarbeitung und wenn die MAPI-Warteschlange **SubmitMessage** aufruft, wenn es vorverarbeitung wurde.</span><span class="sxs-lookup"><span data-stu-id="66f03-132">The following two steps occur in the client process if there was no preprocessing, and when the MAPI spooler calls **SubmitMessage** if there was preprocessing.</span></span> 

<span data-ttu-id="66f03-133">**Die Nachricht Speicheranbieter**:</span><span class="sxs-lookup"><span data-stu-id="66f03-133">**The message store provider**:</span></span>

1. <span data-ttu-id="66f03-134">Performs the following tasks if the message store is tightly coupled to a transport and the NEEDS_SPOOLER flag was returned from [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md):</span><span class="sxs-lookup"><span data-stu-id="66f03-134">Performs the following tasks if the message store is tightly coupled to a transport and the NEEDS_SPOOLER flag was returned from [IMAPISupport::ExpandRecips](imapisupport-expandrecips.md):</span></span>
    
   - <span data-ttu-id="66f03-135">Verarbeitet Empf�nger, die es verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="66f03-135">Handles any recipients that it can handle.</span></span>
   - <span data-ttu-id="66f03-136">Legt die **PR_RESPONSIBILITY** -Eigenschaft auf TRUE fest, f�r alle Empf�nger, die sie behandelt.</span><span class="sxs-lookup"><span data-stu-id="66f03-136">Sets the **PR_RESPONSIBILITY** property to TRUE for any recipients that it handles.</span></span> 
   - <span data-ttu-id="66f03-137">F�hrt die folgenden Aufgaben aus, wenn alle Empf�nger zu diesem eng gekoppelten Store und Transport bekannt sind:</span><span class="sxs-lookup"><span data-stu-id="66f03-137">Performs the following tasks if all recipients are known to this tightly coupled store and transport:</span></span>
     - <span data-ttu-id="66f03-138">IMAPISupport::CompleteMsg aufgerufen, wenn die Nachricht vorverarbeitet wurde oder die Nachrichtenspeicher Anbieter möchte der MAPI-Warteschlange für die Durchführung Verarbeitung von Nachrichten, wird empfohlen, damit messaging, dass Haken aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="66f03-138">Calls IMAPISupport::CompleteMsg if the message was preprocessed or the message store provider wants the MAPI spooler to complete message processing which is recommended so that messaging hooks can be invoked.</span></span> <span data-ttu-id="66f03-139">Nachrichtenfluss wird die MAPI-Warteschlange fort, wie im folgenden Verfahren beschrieben.</span><span class="sxs-lookup"><span data-stu-id="66f03-139">Message flow continues with the MAPI spooler as described in the following procedure.</span></span>  
     - <span data-ttu-id="66f03-140">Führt die folgenden Aufgaben aus, wenn die Nachricht nicht vorverarbeitet wurde oder der Nachricht Speicheranbieter nicht die MAPI-Warteschlange zum Abschließen der Verarbeitung von Nachrichten möchte:</span><span class="sxs-lookup"><span data-stu-id="66f03-140">Performs the following tasks if the message was not preprocessed or the message store provider does not want the MAPI spooler to complete message processing:</span></span>
       - <span data-ttu-id="66f03-141">Kopien legen Sie die Nachricht in den Ordner, der durch die Eintrags-ID in der Eigenschaft PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId), sofern bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="66f03-141">Copies the message to the folder identified by the entry identifier in the PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId) property, if set.</span></span>
       - <span data-ttu-id="66f03-142">Löscht die Nachricht, wenn die PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit)-Eigenschaft auf TRUE festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="66f03-142">Deletes the message if the PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit) property has been set to TRUE.</span></span>
       - <span data-ttu-id="66f03-143">Entsperrt die Nachricht, wenn sie gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="66f03-143">Unlocks the message if it is locked.</span></span>
       - <span data-ttu-id="66f03-144">Gibt an den Client.</span><span class="sxs-lookup"><span data-stu-id="66f03-144">Returns to the client.</span></span> <span data-ttu-id="66f03-145">Nachrichtenfluss ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="66f03-145">Message flow is complete.</span></span> 
   
2. <span data-ttu-id="66f03-146">F�hrt die folgenden Aufgaben aus, wenn der Nachrichtenspeicher nicht eng um einen Transport verkn�pft, nicht alle Empf�nger mit dem Nachrichtenspeicher bezeichnet wurden oder das Flag NEEDS_SPOOLER festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="66f03-146">Performs the following tasks if the message store is not tightly coupled to a transport, not all of the recipients were known to the message store, or the NEEDS_SPOOLER flag is set:</span></span>
    
   - <span data-ttu-id="66f03-147">Versetzt die Nachricht in der ausgehenden Warteschlange ohne das SUBMITFLAG_PREPROCESS Bit in der **PR_SUBMIT_FLAGS** -Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="66f03-147">Puts the message in the outgoing queue without setting the SUBMITFLAG_PREPROCESS bit in the **PR_SUBMIT_FLAGS** property.</span></span> 
   - <span data-ttu-id="66f03-148">Benachrichtigt die MAPI-Warteschlange, die die ausgehende Warteschlange ge�ndert wurde, indem eine Benachrichtigung �ber eine Tabelle zu generieren.</span><span class="sxs-lookup"><span data-stu-id="66f03-148">Notifies the MAPI spooler that the outgoing queue has changed by generating a table notification.</span></span> 
   - <span data-ttu-id="66f03-149">Gibt f�r den Client und Nachrichtenfluss weiterhin mit einem Satz von Aufgaben, die MAPI-Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="66f03-149">Returns to the client, and message flow continues with a set of tasks performed by the MAPI spooler.</span></span>
    
<span data-ttu-id="66f03-p107">Wenn eine Nachricht von den MAPI-Warteschlange verarbeitet werden, wird der Nachricht Speicheranbieter die Nachricht **PR_SUBMIT_FLAGS** -Eigenschaft auf SUBMITFLAG_LOCKED. Das SUBMITFLAG_LOCKED-Flag gibt an, dass die MAPI-Warteschlange die Nachricht zur ausschlie�lichen Verwendung gesperrt hat. Der andere Wert f�r **PR_SUBMIT_FLAGS,** SUBMITFLAG_PREPROCESS, wird festgelegt, wenn die Nachricht muss Vorverarbeitung durch eine oder mehrere Pr�prozessor � Funktionen, die von einem Transportanbieter registriert.</span><span class="sxs-lookup"><span data-stu-id="66f03-p107">When a message is to be handled by the MAPI spooler, the message store provider sets the message's **PR_SUBMIT_FLAGS** property to SUBMITFLAG_LOCKED. The SUBMITFLAG_LOCKED flag indicates that the MAPI spooler has locked the message for its exclusive use. The other value for **PR_SUBMIT_FLAGS,** SUBMITFLAG_PREPROCESS, is set when the message requires preprocessing by one or more preprocessor functions registered by a transport provider.</span></span> 
  
