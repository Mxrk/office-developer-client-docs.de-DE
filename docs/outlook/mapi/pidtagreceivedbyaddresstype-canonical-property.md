---
title: Kanonische PidTagReceivedByAddressType-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedByAddressType
api_type:
- COM
ms.assetid: 0eef299d-6923-4dae-9a18-91ea82ea0f3e
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 96a53e427460990983242009500ade9ae0c5ada5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794867"
---
# <a name="pidtagreceivedbyaddresstype-canonical-property"></a>Kanonische PidTagReceivedByAddressType-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält den e-Mail-Adresse ein, beispielsweise SMTP, für den messaging-Benutzer, der tatsächlich die Nachricht empfängt.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_RECEIVED_BY_ADDRTYPE, PR_RECEIVED_BY_ADDRTYPE_A, PR_RECEIVED_BY_ADDRTYPE_W  <br/> |
|Bezeichner:  <br/> |0x0075  <br/> |
|Datentyp:  <br/> |PT_STRING8, PT_UNICODE  <br/> |
|Bereich:  <br/> |MAPI-Umschlag  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaften sind Beispiele für die Adresseigenschaften für den messaging-Benutzer, der tatsächlich die Nachricht empfängt. Sie müssen von der eingehenden Adressbuchhierarchie festgelegt werden.
  
Die Typ Adresszeichenfolge kann nur Großbuchstaben A bis Z und die Zahlen null bis neun enthalten. Diese Eigenschaften kennzeichnen die **PR_RECEIVED_BY_EMAIL_ADDRESS** ([PidTagReceivedByEmailAddress](pidtagreceivedbyemailaddress-canonical-property.md))-Eigenschaft angeben einen Adresstyp, beispielsweise SMTP, wodurch, die angibt, wie die Adresse erstellt werden soll.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für e-Mail-Nachrichten zulässig sind.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
Mapitags.h
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

