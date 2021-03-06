---
title: Kanonische PidLidAddressBookProviderEmailList-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAddressBookProviderEmailList
api_type:
- COM
ms.assetid: 9c0527ea-e922-4514-b913-d3520350c452
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 4eb2897c1834715f3d937ef7946998943b386aef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793357"
---
# <a name="pidlidaddressbookprovideremaillist-canonical-property"></a>Kanonische PidLidAddressBookProviderEmailList-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt an, welche Eigenschaften für e-Mail-Adresse auf den Kontakt festgelegt sind. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidABPEmailList  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Address  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008028  <br/> |
|Datentyp:  <br/> |PT_MV_LONG  <br/> |
|Bereich:  <br/> |Kontakt  <br/> |
   
## <a name="remarks"></a>Hinweise

Jeder PT_LONG Wert in dieser Eigenschaft muss in der Eigenschaft eindeutig sein und muss auf einen der Werte in der folgenden Tabelle festgelegt werden. Wenn diese Eigenschaft festgelegt ist, muss auch die **DispidABPArrayType** ([PidLidAddressBookProviderArrayType](pidlidaddressbookproviderarraytype-canonical-property.md))-Eigenschaft festgelegt werden. Diese beiden Eigenschaften müssen miteinander synchronisiert werden. Angenommen, wenn einer der Werte in **DispidABPEmailList** "0 x 00000000" **DispidABPArrayType** ist, muss das Bit "0 x 00000001" festgelegt haben. 
  
|**Wert**|**Beschreibung**|
|:-----|:-----|
|0x00000000  <br/> |Email1 ist für den Kontakt definiert.  <br/> |
|0x00000001  <br/> |Email2 ist für den Kontakt definiert.  <br/> |
|0x00000002  <br/> |Email3 ist für den Kontakt definiert.  <br/> |
|0 x 00000003  <br/> |Fax (geschäftlich) ist für den Kontakt definiert.  <br/> |
|0 x 00000004  <br/> |Fax privat ist für den Kontakt definiert.  <br/> |
|0 x 00000005  <br/> |Primäre Faxnummer ist für den Kontakt definiert.  <br/> |
   
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Operationen, die für Kontakte und persönliche Verteilerlisten zulässig sind.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

