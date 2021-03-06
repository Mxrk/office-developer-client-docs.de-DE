---
title: DNTBL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 77835b48-43aa-8518-9712-754e84f1e713
description: 'Letzte �nderung: Donnerstag, 5. Juli 2012'
ms.openlocfilehash: 6096118d72dfc51fb60025a55f581ebf97b000a7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791590"
---
# <a name="dntbl"></a>DNTBL
 
**Betrifft**: Outlook 
  
Informationen für das Herunterladen von den Inhalt eines Ordners auf dem Server während der [Tabelle Downloadstatus](download-table-state.md), als Teil einer vollständigen Synchronisierung für Inhalt in einem Speicher.
  
## <a name="quick-info"></a>QuickInfo

```cpp
struct DNTBL 
{ 
    ULONG ulFlags; 
    LPSTREAM pstmReserved1; 
    LPSTREAM pstmReserved2; 
    LPSTREAM pstmReserved3; 
    LPSTREAM pstmReserved4; 
    PXICC pxicc; 
    PXIHC pxihc; 
    LPSTR pszName; 
    FILETIME ftLastMod; 
    ULONG ulRights; 
    FEID feid; 
    UINT uintReserved; 
    DNTBLE rgte[2]; 
    LPSRestriction psrReserved; 
    BOOL boReserved; 
    void* pReserved1; 
    void* pReserved2; 
};

```

## <a name="members"></a>Members

_ulFlags_
  
> [in] Flags Ändern des Verhaltens 
    
  - DNT_OK
    
    - [in] Download war erfolgreich. Der Client legt dies nach dem Herunterladen von Informationen vom Server.
    
_pstmReserved1_
  
> [out] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_pstmReserved2_
  
> [out] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_pstmReserved3_
  
> [out] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_pstmReserved4_
  
> [out] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_pxicc_
  
>  [out] Zeiger auf die **IExchangeImportContentsChanges** Inhalt-Schnittstelle unterstützt, Herunterladen von Änderungen. Weitere Informationen zu **IExchangeImportContentsChanges**finden Sie unter [ICS Bewertungskriterien](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).
    
_pxihc_
  
>  [out] Zeiger auf die **IExchangeImportHierarchyChanges** Hierarchie-Schnittstelle unterstützt, die Hierarchie inkrementelle Änderungen herunterladen. Weitere Informationen zu **IExchangeImportHierarchyChanges**finden Sie unter [ICS Bewertungskriterien](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).
    
_pszName_
  
>  [out] Name des Ordners. 
    
_ftLastMod_
  
>  [out] Zeitpunkt der letzten Änderung des Ordners. 
    
_ulRights_
  
>  [out] Der Wert der Eigenschaft **[PR_RIGHTS](http://msdn.microsoft.com/en-us/library/ee238052%28v=EXCHG.80%29.aspx)** des Ordners. 
    
_feid_
  
>  [out] Die EntryID des Ordners. 
    
_uintReserved_
  
>  [out] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_rgte_
  
> [out] Änderungen für normalen (oder nicht ausgeblendeten) und zugeordneten (oder ausgeblendet) Elemente.  *Rgte [0]* ist für normale Elemente und *Rgte [1]* ist für verknüpfte Objekte. Outlook wird dieser Member während des Herunterladens, wenn Sie inkrementelle Änderung Synchronisierung (ICS) verwenden. Weitere Informationen zu ICS finden Sie unter [ICS Bewertungskriterien](http://msdn.microsoft.com/en-us/library/aa579252%28EXCHG.80%29.aspx).
    
_lpsrReserved_
  
>  [in] / [out] dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_boReserved_
  
>  [in] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_pReserved1_
  
>  [out] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
_pReserved2_
  
>  [in] Dieser Member wird für die interne Verwendung von Outlook reserviert und wird nicht unterstützt. 
    
## <a name="see-also"></a>Siehe auch

- [Informationen zu den Replikationsstatus Computer](about-the-replication-state-machine.md)  
- [MAPI-Konstanten](mapi-constants.md) 
- [DNTBLE](dntble.md)

