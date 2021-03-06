---
title: Kanonische PidLidTaskAssigner-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskAssigner
api_type:
- COM
ms.assetid: f7047e4e-0fb3-476b-9568-8f1135e6d970
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 5b711b1e0db0fab93016d3f1c979d81a142c9946
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793818"
---
# <a name="pidlidtaskassigner-canonical-property"></a>Kanonische PidLidTaskAssigner-Eigenschaft

  
  
**Betrifft**: Outlook 
  
 Namen der Benutzer, der zuletzt verwendet wurde die Aufgabe zugewiesen. 
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |dispidTaskDelegator  <br/> |
|-Eigenschaft festgelegt:  <br/> |PSETID_Task  <br/> |
|Long-ID (Abdeckung):  <br/> |0x00008121  <br/> |
|Datentyp:  <br/> |PT_UNICODE  <br/> |
|Bereich:  <br/> |Aufgabe  <br/> |
   
## <a name="remarks"></a>Hinweise

Wenn die Aufgabe nicht zugewiesen wurde, bleibt diese Eigenschaft nicht festgelegt. Da der Client diese Eigenschaft festlegt, nachdem Beauftragte für die Aufgabe eine Aufgabenanfrage erhalten, wird die Eigenschaft nicht auf die Aufgabe delegierende Person Kopie der Aufgabe festgelegt werden. Wenn der Client hinzugefügt oder entfernt eine Aufgabe delegierende Person aus der Aufgabenliste delegierende Person in der Eigenschaft **DispidTaskMyDelegators** ([PidLidTaskAssigners](pidlidtaskassigners-canonical-property.md)), die **DispidTaskDelegator** ([PidLidTaskAssigner](pidlidtaskassigner-canonical-property.md))-Eigenschaft muss auf das hinzugefügte festgelegt oder entfernte Aufgabe delegierende Person.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> Mehrere Objekte, die das elektronische Äquivalent von Aufgaben, vorgangszuordnungen und vorgangsaktualisierungen Modell definiert.
    
### <a name="header-files"></a>Header-Dateien

Mapidefs.h
  
> Enthält die Datentypdefinitionen.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

