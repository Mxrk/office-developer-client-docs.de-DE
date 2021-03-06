---
title: IProfAdminGetProfileTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.GetProfileTable
api_type:
- COM
ms.assetid: cebccd2d-8215-486e-9964-7fc42412cec6
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: c942bdbf27590dde04b84970e345f265bc645045
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792762"
---
# <a name="iprofadmingetprofiletable"></a>IProfAdmin::GetProfileTable

  
  
**Betrifft**: Outlook 
  
Bietet Zugriff auf die Benutzerprofildienst-Tabelle eine Tabelle mit Informationen zu allen verfügbaren Profilen.
  
```cpp
HRESULT GetProfileTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>Parameter

 _ulFlags_
  
> [in] Immer NULL.
    
 _lppTable_
  
> [out] Ein Zeiger auf einen Zeiger auf die Benutzerprofildienst-Tabelle.
    
## <a name="return-value"></a>R�ckgabewert

S_OK 
  
> Die Profiltabelle wurde erfolgreich abgerufen.
    
## <a name="remarks"></a>Hinweise

Die **IProfAdmin::GetProfileTable** -Methode ermöglicht den Zugriff auf die Benutzerprofildienst-Tabelle, die enthält eine Zeile für jedes verfügbaren Profil. Es gibt nur zwei Spalten in jeder Zeile: Anzeigename den Namen des Profils und ein Flag, das angibt, ob das Profil der Standardwert ist. 
  
Profile, die gelöscht oder, die verwendet werden, aber zum Löschen markiert wurden, sind nicht in der Profiltabelle enthalten. Die Benutzerprofildienst-Tabelle ist statisch. nachfolgende hinzufügen und Löschen von Profilen werden in der Tabelle nicht wiedergegeben. 
  
Wenn keine Profile vorhanden ist, gibt **"GetProfileTable"** eine Tabelle mit 0 (null) Zeilen zurück. 
  
Weitere Informationen zu der Tabelle "Profil" finden Sie unter [Profil Tabellen](profile-tables.md). 
  
## <a name="mfcmapi-reference"></a>MFCMAPI (engl.) (engl.)

Beispielcode MFCMAPI (engl.) finden Sie in der folgenden Tabelle.
  
|**Datei**|**Funktion**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnShowProfiles  <br/> |MFCMAPI (engl.) verwendet die **IProfAdmin::GetProfileTable** -Methode zum Abrufen der Benutzerprofildienst-Tabelle in ein neues Dialogfeld angezeigt.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[IMAPITable: IUnknown](imapitableiunknown.md)
  
[MAPILogonEx](mapilogonex.md)
  
[IProfAdmin: IUnknown](iprofadminiunknown.md)


[MFCMAPI (engl.) als ein Codebeispiel](mfcmapi-as-a-code-sample.md)

