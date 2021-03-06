---
title: Kanonische PidTagExchangeProfileSectionId-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagExchangeProfileSectionId
api_type:
- HeaderDef
ms.assetid: 4ad2f417-be8f-4fc8-9321-82097289074b
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 37a318df01101487fe0e8970251201c2515d1e8a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794345"
---
# <a name="pidtagexchangeprofilesectionid-canonical-property"></a>Kanonische PidTagExchangeProfileSectionId-Eigenschaft

  
  
**Betrifft**: Outlook 
  
Enthält eine dynamisch generierte GUID verwendet, um ein Konto zu bestimmen, wann Sie mehrere Microsoft Exchange Server-Konten verwenden.
  
|||
|:-----|:-----|
|Zugeordneten Eigenschaften:  <br/> |PR_EMSMDB_SECTION_UID  <br/> |
|Bezeichner:  <br/> |0x3d150102  <br/> |
|Datentyp:  <br/> |PT_BINARY  <br/> |
|Bereich:  <br/> |Mehrere Exchange-Konten  <br/> |
   
## <a name="remarks"></a>Hinweise

Microsoft Outlook 2010 und Microsoft Outlook 2013 unterstützen mehrerer Exchange-Konten anstelle von einem einzelnen Exchange-Konto. Um mehrere Exchange-Konten zu unterstützen, wurde das MAPI-Profil Layout geändert. In Microsoft Office Outlook 2007 und früheren Versionen enthalten Profile feste Profile-Abschnitt für Exchange-Einstellungen wie Servernamen, Benutzernamen und Offlineordnerdatei (OST). Speicherort. Diese Einstellungen wurden über einen eindeutigen Bezeichner, der **PbGlobalProfileSectionGuid** -Eigenschaft identifiziert. Im Abschnitt für die Exchange-Einstellungen verwendet wird Abschnitts Profile globale Exchange aufgerufen. Weitere Informationen über die globale Exchange-Profil in Outlook 2007 finden Sie unter [globale Abschnitt Profile zu öffnen](http://support.microsoft.com/kb/188482).
  
Ein festen Profil im Abschnitt Speicherort ist nicht mehr ausreichend, um mehrere Exchange-Konten aufzunehmen. Stattdessen vorhanden ist für jede Exchange-Konto in Ihrem Benutzerprofil ein Abschnitt, der auf die Einstellungen für dieses Konto vorgesehen ist. Der neue Abschnitt für die Exchange-Einstellungen verwendet wird durch die eindeutige ID **EmsmdbUID**identifiziert.
  
In der Nachricht Profilabschnitt für die Exchange-Konto finden Sie eine Eigenschaft, die eine GUID enthält, die dynamisch zu dem Zeitpunkt generiert wird, die das Konto erstellt wird. Diese GUID wird in der **PidTagExchangeProfileSectionId** -Eigenschaft gespeichert. Nachrichtenspeicher und Address Book Container verfügbar machen, eine Eigenschaft, um die Exchange-Konto zu bestimmen, zu dem sie gehören. In der Tabelle der Dienste zugänglich, jeden Exchange-Dienst macht diese Eigenschaft. 
  
Sie können diese Eigenschaft durch einen Aufruf von [IMAPIProp::GetProps](imapiprop-getprops.md) auf **PidTagExchangeProfileSectionId** abrufen, nachdem Sie Abfragen aus einem der folgenden Schnittstellen: 
  
- [IMsgStore: IMAPIProp](imsgstoreimapiprop.md)
    
- [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)
    
- [IABContainer: IMAPIContainer](iabcontainerimapicontainer.md)
    
Wenn das Objekt nicht mit Exchange angegliedert ist, gibt der Aufruf **MAPI_E_NOT_FOUND**zurück.
  
Beim Anzeigen des Adressbuchs können Sie Container in einer **PidTagExchangeProfileSectionId** einschränken. Nachdem Sie einen Container geöffneten haben, können Sie die **EmsmdbUID** daraus Abfragen. Es ist außerdem zu beachten, dass wenn ein Empfänger aus einem Exchange-Adressbuch ausgewählt wurde, der Empfänger auch die **PidTagExchangeProfileSectionId** in der Liste der Eigenschaften verfügt. 
  
> [!NOTE]
> Diese GUID wird in der Codebeispiele und Funktion Kopfzeilen als **EmsmdbUID**bezeichnet. 
  
Eines der Exchange-Konten ist mit der Exchange-Vorversionskonten gekennzeichnet. Normalerweise ist es das erste Konto dem Profil hinzugefügt. Alle Anrufe **PbGlobalProfileSectionGuid** geöffnet wird an die globale Exchange-Abschnitt des legacy-Kontos umgeleitet. Die Objektmodellaufrufe, die Interaktion mit nicht-Legacy-Exchange-Konto interagieren Sie auch mit der legacy-Exchange-Konto. 
  
Ältere Exchange-Dienst hat die Eigenschaft **PR_EMSMDB_LEGACY** (0x3D18000B), die auf **"true"** in der Tabelle der Dienste festgelegt ist. 
  
Der Vorversion **EmsmdbUID** wird auch als **PidTagExchangeProfileSectionId**in der globalen Profil im Abschnitt Outlook des Profils versehen. Zur Unterstützung mehrerer Exchange-Konten geschriebene Code sollte keinen der Vorversion **EmsmdbUID** abgerufen werden, da es die richtige **EmsmdbUID**, je nach dem Konto abrufen soll, Ihr Code interagiert.
  
## <a name="see-also"></a>Siehe auch



[Verwenden mehrerer Exchange-Konten](using-multiple-exchange-accounts.md)


[How To Open the Global Profile Section](http://support.microsoft.com/kb/188482)

