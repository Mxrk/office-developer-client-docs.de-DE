---
title: FreeProws
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- FreeProws
api_type:
- HeaderDef
ms.assetid: 0f8f9fc4-4940-4c0a-92cc-2a6409b9a13f
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 93659a28969efd0d04e9fc44f8926e89586f7773
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791748"
---
# <a name="freeprows"></a>FreeProws

  
  
**Betrifft**: Outlook 
  
Löscht eine [SRowSet](srowset.md) -Struktur und zugehörige Speicher, einschließlich des Speichers für alle Member Arrays und Strukturen frei. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapiutil.h  <br/> |
|Implementiert von:  <br/> |MAPI  <br/> |
|Aufgerufen von:  <br/> |Clientanwendungen und -Dienstanbieter  <br/> |
   
```cpp
void FreeProws(
  LPSRowSet prows
);
```

## <a name="parameters"></a>Parameter

 _PROWS_
  
> [in] Zeiger auf die **SRowSet** -Struktur, die gelöscht werden. 
    
## <a name="return-value"></a>Rückgabewert

None.
  
## <a name="notes-to-callers"></a>Hinweise für Aufrufer

Als Teil der Implementierung der **FreeProws**ruft MAPI [MAPIFreeBuffer](mapifreebuffer.md) -Funktion, um alle Einträge in der Struktur **SRowSet** freizugeben, bevor die vollständige Struktur freigegeben. Aus diesem Grund alle diese Einträge müssen die Zuweisung Regeln für die [SRowSet](srowset.md) -Struktur folgen, mit einer einzelnen [MAPIAllocateBuffer](mapiallocatebuffer.md) rufen Sie für jedes Array mit Mitgliedern und Struktur. 
  
Weitere Informationen zum Zuweisen von Arbeitsspeicher für **ADRLIST** und **SRowSet** Strukturen finden Sie unter [Verwalten von Arbeitsspeicher für ADRLIST und SRowSet Strukturen](managing-memory-for-adrlist-and-srowset-structures.md). 
  
## <a name="mfcmapi-reference"></a>MFCMAPI (engl.) (engl.)

Beispielcode MFCMAPI (engl.) finden Sie in der folgenden Tabelle.
  
|**Datei**|**Funktion**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> |DwThreadFuncLoadTable  <br/> |MFCMAPI (engl.) verwendet die **FreeProws** -Methode, um eine SRowSet-Struktur, die Zeilen der Tabelle verarbeitet enthält frei.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[MFCMAPI (engl.) als ein Codebeispiel](mfcmapi-as-a-code-sample.md)

