---
title: Kanonische PidLidReminderDelta-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidReminderDelta
api_type:
- COM
ms.assetid: 011d73d0-8b38-4a4e-a56f-92dec451946a
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: e2caccf3cf6ca7e6f15bed1c901d4dfbb198f19b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793726"
---
# <a name="pidlidreminderdelta-canonical-property"></a>Kanonische PidLidReminderDelta-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Gibt das Intervall in Minuten zwischen dem Zeitpunkt, wann die Erinnerung zuerst überfällig wird, und die Anfangszeit des Calendar-Objekt an.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidReminderDelta  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Common  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008501  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Erinnerung  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft muss auf Kalender-Objekte festgelegt werden. Für alle Objekte, nicht-Kalender wird diese Eigenschaft auf "0 x 00000000" festgelegt werden und wird ignoriert. Wenn eine Erinnerung für eine Instanz von sich wiederholenden Calendar-Objekt geschlossen ist, wird der Wert dieser Eigenschaft in der Berechnung der Zeit Signal an die nächste Instanz verwendet. Einzelheiten über das Erstellen von Calendar-Objekt finden Sie unter [[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx) . 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXORMDR]](http://msdn.microsoft.com/library/5454ebcc-e5d1-4da8-a598-d393b101caab%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und das Interaktionsmodell für e-Mail und anderen Objekt Erinnerungen.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

