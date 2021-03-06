---
title: Kanonische PidLidBusyStatus-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBusyStatus
api_type:
- COM
ms.assetid: 50c91fe6-2a61-4348-a16d-fd5c501b0715
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 926f0425a4a59cad4280917573c974375c94f50b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793456"
---
# <a name="pidlidbusystatus-canonical-property"></a>Kanonische PidLidBusyStatus-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Die Verfügbarkeit des Benutzers für einen Termin darstellt.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidBusyStatus  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Appointment  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008205  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Kalender  <br/> |
   
## <a name="remarks"></a>Hinweise

Diese Eigenschaft gibt die Verfügbarkeit eines Benutzers für das Ereignis, das durch das Objekt beschrieben und muss einer der unten angegebenen Werte.
  
|**Wert**|**Beschreibung**|
|:-----|:-----|
|0x00000000  <br/> |Der Benutzer ist verfügbar.  <br/> |
|0x00000001  <br/> |Der Benutzer hat ein mit Vorbehalt Ereignis geplant.  <br/> |
|0x00000002  <br/> |Der Benutzer ist ausgelastet.  <br/> |
|0 x 00000003  <br/> |Der Benutzer befindet sich nicht im Büro.  <br/> |
   
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOCAL]](http://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für den Termin, einer Besprechungsanfrage und Antwortnachrichten.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

