---
title: DTPAGE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTPAGE
api_type:
- COM
ms.assetid: 500f60ed-fdec-4d70-8cf5-664c46643956
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a187245b2594282bc9908b3075852440f418af2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791629"
---
# <a name="dtpage"></a>DTPAGE

  
  
**Betrifft**: Outlook 
  
Beschreibt das Dialogfeld, die aus einer Tabelle anzeigen von der Funktion [BuildDisplayTable](builddisplaytable.md) erstellt wird. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct DTPAGE
{
  ULONG cctl;
  LPSTR lpszResourceName;
  union
  {
    LPSTR lpszComponent;
    ULONG ulItemID;
  }
  LPDTCTL lpctl;
} DTPAGE, FAR *LPDTPAGE;

```

## <a name="members"></a>Members

 **cctl**
  
> Anzahl der Steuerelemente auf das Element **Lpctl** zeigt. 
    
 **lpszResourceName**
  
> Zeiger auf den Namen oder die ganze Zahl Bezeichner für die Feld-Ressource. 
    
 **lpszComponent**
  
> Zeiger auf die Zeichenfolge, die im Abschnitt **[Help File Mappings]** in MAPISVC.INF angezeigt wird. Da **LpszComponent** in einer Union mit dem **UlItemID** -Element ist, muss nur einer der folgenden Member gültige Daten. 
    
 **ulItemID**
  
> Ganzzahlige Ressourcenbezeichner mit kleiner oder gleich 65535, von denen der Name der Hilfedatei gelesen werden kann. Da **UlItemID** in einer Union mit dem **LpszComponent** -Element ist, muss nur einer der folgenden Member gültige Daten. 
    
 **lpctl**
  
> Zeiger auf ein Array von [DTCTL](dtctl.md) -Strukturen, einen für jedes Steuerelements auf der Seite. 
    
## <a name="remarks"></a>Hinweise

Legen Sie die Hilfedatei für die Seite um zu ermitteln, **LpszComponent** Mitglieds eine hartcodierte Zeichenfolge oder der **UlItemID** Member zu einem ganzzahligen Ressourcenbezeichner. 
  
Jeder Eintrag im Abschnitt **[Help File Mappings]** in MAPISVC. INF-Datei besteht aus einer Zeichenfolge Komponente, die nicht mehr als 30 Zeichen, klicken Sie auf der linken Seite und ein Hilfe Dateipfad auf der rechten Seite. **UlItemID** und **LpszResourceName** sind im _hInstance_ -Parameter der **BuildDisplayTable**gefunden. Weitere Informationen finden Sie unter [MAPISVC. INF [Hilfe Dateizuordnungen] Abschnitt](mapisvc-inf-help-file-mappings-section.md).
  
Obwohl **BuildDisplayTable** diese Struktur verwendet, um der Anzeige-Tabelle aus der Steuerelementressourcen, erstellen die Struktur **DTPAGE** wird nie angezeigt, in der Anzeige Tabelle selbst. 
  
Eine Übersicht über die Anzeige Tabellen finden Sie unter [Tabellen angezeigt](display-tables.md). Informationen zum Implementieren einer Tabelle anzeigen finden Sie unter [Implementieren einer Tabelle anzuzeigen](display-table-implementation.md).
  
## <a name="see-also"></a>Siehe auch



[BuildDisplayTable](builddisplaytable.md)
  
[DTBLPAGE](dtblpage.md)
  
[DTCTL](dtctl.md)


[MAPI-Strukturen](mapi-structures.md)

