---
title: CONTAB_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 84251222-dac4-4f4d-97b9-aa0e2cd26c44
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 2c8661f24ed9555547446cf63fc08a3be7e6e941
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791436"
---
# <a name="contabentryid"></a>CONTAB_ENTRYID

  
  
**Betrifft**: Outlook 
  
Enthält die Eintrags-ID für den Kontakteordner.
  
|||
|:-----|:-----|
|Headerdatei  <br/> |msomapiutil.h  <br/> |
   
```cpp
#pragma pack(4) 
typedef struct _contab_entryid
{
    BYTE abFlags[4];
    MAPIUID muid;
    ULONG ulVersion;
    ULONG ulType;
    ULONG ulIndex;
    ULONG cbeid;
    BYTE abeid[1];
}   CONTAB_ENTRYID, *LPCONTAB_ENTRYID;
#pragma pack() 
```

## <a name="members"></a>Members

 **abFlags**
  
> Eine Bitmaske aus Flags, die Informationen für das Objekt bereitstellt. Weitere Informationen finden Sie unter der Beschreibung des Felds **AbFlags** einer [ENTRYID](entryid.md) -Struktur. 
    
 **muid**
  
> GUID, den Speicheranbieter identifiziert.
    
 **ulVersion**
  
> Die Versionsnummer der **CONTAB_ENTRYID** Struktur. Muss auf CONTAB_VERSION festgelegt sein. 
    
 **ulType**
  
> Eine ganze Zahl, die den Kontakteintrag ID-Typ darstellt. Es muss eine der folgenden Werte sein:
    
|**Name**|**Beschreibung**|
|:-----|:-----|
|CONTAB_USER  <br/> |Ein messaging User-Objekt.  <br/> |
|CONTAB_DISTLIST  <br/> |Verteilung von List-Objekt.  <br/> |
   
 **ulIndex**
  
> Der Index der Teilmenge der e-Mail-Eigenschaft.
    
 **cbeid**
  
> Die Größe des Eintrags-ID der Nachricht Kontakt im Adressbuch Kontakte Eintrag zugeordnet.
    
 **abeid**
  
> Der Eintrag Bezeichner der Nachricht Kontakt im Adressbuch Kontakte Eintrag zugeordnet.
    
## <a name="remarks"></a>Hinweise

Einem Adressbuch Kontakte ist ein Adressbuch, das alle Kontaktelemente in einem Kontakteordner enthält, die eine e-Mail-Adresse oder eine Faxnummer verfügen. Jeder Eintrag in einem Adressbuch Kontakte ist eine e-Mail-Adresse oder eine Faxnummer zugeordnet. Da ein Kontaktelement kann bis zu drei e-Mail-Adressen und drei Faxnummer, kann ein Kontaktelement durch maximal sechs Einträge in der entsprechenden Kontaktadressbuch dargestellt werden.
  
Einem Adressbuch Kontakte dient zur Unterstützung von Benutzern, die Adressierung von e-Mail-Nachrichten an Kontakte in einem Kontakteordner. Der Adressbuch Kontakte-Anbieter, die Unterstützung von Microsoft Outlook 2010 und Microsoft Outlook 2013 ist contab32.dll.
  
Die Struktur **CONTAB_ENTRYID** unterstützt eine Teilmenge der Informationen, die in der zugrunde liegenden MAPI-Kontakt Nachricht vorhanden ist. Identifiziert die Kontakt-Nachricht, der ein bestimmter Eintrag Adressbuch Kontakte zugeordnet ist. 
  
Die Felder **Cbeid** und **Abeid** sind nur gültig, wenn der Wert des Felds **UlType** auf CONTAB_DISTLIST oder CONTAB_USER festgelegt ist. Wenn der Wert des Felds **UlType** CONTAB_ROOT, CONTAB_SUBROOT oder CONTAB_CONTAINER festgelegt ist, sollte die Struktur [DIR_ENTRYID](dir_entryid.md) stattdessen verwendet werden. 
  
## <a name="see-also"></a>Siehe auch



[DIR_ENTRYID](dir_entryid.md)


[MAPI-Strukturen](mapi-structures.md)

