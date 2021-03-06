---
title: MAPI-Schnittstellen
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: 34a66cf0-b4e0-4fd5-b937-cd157888961d
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: e485079de800c63b02d71b3c3ccb90d66101c64b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793015"
---
# <a name="mapi-interfaces"></a>MAPI-Schnittstellen

  
  
**Betrifft**: Outlook 
  
Die Dokumentation f�r jede Schnittstelle besteht aus einem einleitenden Abschnitt, der eine kurze Beschreibung des Zwecks der Schnittstelle enth�lt, , gefolgt von einer Tabelle, die die folgenden Informationen enth�lt.
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Die Headerdatei, in der die Schnittstelle definiert ist, und die beim Kompilieren des Quellcodes einbezogen werden muss.  <br/> |
|Verf�gbar gemacht von:  <br/> |Das Objekt, das die Schnittstelle verf�gbar macht.  <br/> |
|Implementiert von:  <br/> |Eine Liste der Komponenten, die eine Implementierung der Schnittstelle bereitstellen.  <br/> |
|Aufgerufen von:  <br/> |Eine Liste der Komponenten, die in der Regel die Methoden der Schnittstelle aufrufen.  <br/> |
|Schnittstellenbezeichner:  <br/> |Die GUID des Schnittstellenbezeichners.  <br/> |
|Zeigertyp:  <br/> |Der Zeigertyp f�r das Objekt, das die Schnittstelle verf�gbar macht.  <br/> |
|Transaktionsmodell:  <br/> |F�r von [IMAPIProp](imapipropiunknown.md) abgeleitete Schnittstellen. Bei �nontransacted" werden die �nderungen sofort wirksam; bei �transacted" werden die �nderungen erst wirksam, wenn [IMAPIProp::SaveChanges](imapiprop-savechanges.md) aufgerufen wird.  <br/> |
   
Nach der ersten Tabelle folgt eine weitere Tabelle, in der alle Methoden dieser Schnittstelle in der vtable-Reihenfolge aufgelistet sind. Bei einer vtable handelt es sich um ein Array von Funktionszeigern, die von dem Compiler mit einem Funktionszeiger f�r jede Methode eines MAPI-Objekts erstellt werden. Die Methoden werden in der gleichen Reihenfolge aufgelistet, in der sie deklariert sind. Methoden, die von anderen Schnittstellen geerbt werden, sind nicht in der Tabelle in vtable-Reihenfolge dargestellt, k�nnen jedoch auf die gleiche Art und Weise verwendet werden, wie in der Schnittstelle dokumentiert, die sie definiert.
  
Nach jedem Schnittstellenthema werden dann die Methoden der Schnittstelle in alphabetischer Reihenfolge dokumentiert. Die Dokumentation umfasst f�r jede Methode umfasst eine kurze Beschreibung des Zwecks, einen Syntaxblock sowie die folgenden Informationen.
  
|**�berschrift**|**Inhalt**|
|:-----|:-----|
|Parameter  <br/> |Eine Beschreibung der einzelnen Parameter in der Methode.  <br/> |
|Rückgabewert  <br/> |Eine Beschreibung der eindeutigen Werte, die die Methode zur�ckgeben kann. Dies sind die Werte, nach denen Anrufer in ihrem Code suchen sollten.  <br/> |
|Hinweise  <br/> |Eine Beschreibung davon, warum und wie die Methode verwendet wird.  <br/> |
|Siehe auch  <br/> |Querverweise zu anderen Themen in dieser Referenz.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[MAPI Reference](mapi-reference.md)

