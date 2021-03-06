---
title: Kanonische PidTagProfileHomeServerFQDN-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 80273b50-bc16-4be2-8471-1a127b6786bb
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 398ff2fd4bab49c8279e198e3efa416c53abda7c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794812"
---
# <a name="pidtagprofilehomeserverfqdn-canonical-property"></a>Kanonische PidTagProfileHomeServerFQDN-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Kerberos-Authentifizierung für eine Benutzerprofildienst-Konfiguration aktiviert.
  
****

|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_PROFILE_HOME_SERVER_FQDN  <br/> |
|Bezeichner:  <br/> |0x662A001F  <br/> |
|Datentyp:  <br/> |PT_UNICODE  <br/> |
|Bereich:  <br/> |MAPI-Profil-Konfiguration  <br/> |
   
## <a name="remarks"></a>Hinweise

Durch Festlegen dieser Eigenschaft auf den Domänennamen des Verzeichnisservers für die Benutzer kann direkte Verbindung zu den Domänencontroller (DC), die für ein Profil erforderlich ist, die Verwendung von Kerberos-Authentifizierung für Microsoft Exchange Server 2007 konfiguriert wurde und früheren Versionen von **RPC_C_AUTHN_GSS_KERBEROS** in **PR_PROFILE_AUTH_PACKAGE**festlegen.
  
> [!NOTE]
> Microsoft Exchange Server 2010 und Exchange Server 2013 behandeln Adresse Adressbuch Aufrufe an den Client Access Server unterschiedlich gegenüber in der Exchange Server 2007 und früheren Versionen deren Verarbeitung. Der DSProxy-Vorgang wird nicht mehr verwendet, damit Kerberos-Authentifizierung erfolgreich ausgeführt werden kann. Jedoch der Client noch mit Exchange-Server und nicht direkt mit dem Domänencontroller, die nicht gewünscht werden möglicherweise kommuniziert werden würde: Einstellung **PR_PROFILE_HOME_SERVER_FQDN** vermeidet dies. 
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.
    
[[MS-OXCSTOR]](http://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> Gibt die zulässige Vorgänge für die Hauptobjekte der Nachricht Store.
    
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

