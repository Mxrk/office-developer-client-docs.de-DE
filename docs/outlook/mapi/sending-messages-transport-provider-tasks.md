---
title: Senden von Nachrichten Transport Anbieter Aufgaben
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bd722f48-b166-4670-8dba-897ac50caf37
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 4625d9d09b067d064dac7ca67b7c79ebb818bcce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795497"
---
# <a name="sending-messages-transport-provider-tasks"></a>Senden von Nachrichten: Transport Anbieter Aufgaben

  
  
**Betrifft**: Outlook 
  
 **Eine Nachricht Anbietern f�r die Daten�bertragung �bermitteln**
  
- Legen Sie die Nachricht **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md))-Eigenschaft auf true fest, nachdem der Adressbuchhierarchie die Nachricht gesendet wurde oder es wurde versucht, die Nachricht zu senden. If an attempt to send a message fails, transport providers should call [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) to generate a nondelivery report. Wenn die Nachricht erfolgreich gesendet, und die **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md))-Eigenschaft auf TRUE festgelegt ist, erstellen Sie eine [ADRLIST](adrlist.md) -Struktur, die die erfolgreiche Empfänger enthält, Festlegen der **PR_DELIVER_TIME** ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md))-Eigenschaft für jede, und rufen Sie **StatusRecips** zum Generieren eines Unzustellbarkeitsberichts. For more information about creating delivery and non-delivery reports, see the following topics: [MAPI-Berichtnachrichten](mapi-report-messages.md), [Erforderliche Bericht Nachrichteneigenschaften](required-report-message-properties.md), [Optional Bericht Nachrichteneigenschaften](optional-report-message-properties.md), and [�bermittlungsberichte Nachricht senden](sending-message-delivery-reports.md).
    
- Legen Sie die Nachricht **PR_SENDER** Gruppe von Eigenschaften auf die Identit�t des Benutzers, der angemeldet hat. Diese Gruppe enthält: **PR_SENDER_ENTRYID** ([PidTagSenderEntryId](pidtagsenderentryid-canonical-property.md)), **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)), **PR_SENDER_SEARCH_KEY** ([PidTagSenderSearchKey](pidtagsendersearchkey-canonical-property.md)), **PR_SENDER_ADDRTYPE** ([ PidTagSenderAddressType](pidtagsenderaddresstype-canonical-property.md)), und **PR_SENDER_EMAIL_ADDRESS** ([PidTagSenderEmailAddress](pidtagsenderemailaddress-canonical-property.md)).
    
- Legen Sie die Nachrichteneigenschaften **PR_SENT_REPRESENTING**, wenn m�glich, um entweder die Identit�t des Benutzers, der angemeldet hat oder auf eine g�ltige Delegaten Identit�t. Die Eigenschaften **PR_SENT_REPRESENTING** dienen zum Implementieren, das Senden von Nachrichten von einem Benutzer im Auftrag eines anderen Benutzers. Anbietern f�r die Daten�bertragung, die diese Eigenschaften nicht unterst�tzen, sollten sie f�r ausgehende Nachrichten ignorieren. 
    
- Legen Sie die Nachricht **PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))-Eigenschaft, um anzugeben, wenn der Client [IMessage::SubmitMessage](imessage-submitmessage.md)aufgerufen.
    
- Legen Sie die Nachricht **PR_PROVIDER_SUBMIT_TIME** ([PidTagProviderSubmitTime](pidtagprovidersubmittime-canonical-property.md))-Eigenschaft an, dass das Datum und die Uhrzeit, zu der der Nachricht Speicheranbieter die Nachricht als müssen gesendet wurde markiert. 
    
Wenn eine Nachricht an eine Vielzahl von Empf�ngern mit verschiedenen Messagingsystemen gesendet wird, wird jede �bertragene Kopie eine anderen Absenderidentit�t haben. 
  
Der Transportdienst oder eng gekoppelten Nachrichtenspeicher und Transport ist auch verantwortlich f�r die Festlegung von Absender und Antwort-an-Informationen. Informationen zum Ersteller ist in den Eigenschaften des **PR_ORIGINATOR** und Antwort-an-Informationen in den Eigenschaften des PR_REPLY gespeichert. Der Client kann diese Eigenschaften festgelegt. jedoch ist der Adressbuchhierarchie zu ignorieren und �berschreiben von Einstellungen f�r den Client zul�ssig. 
  

