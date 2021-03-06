---
title: ITableData IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITableData
api_type:
- COM
ms.assetid: ac7ae09f-ce19-45cf-8963-fad5bba75452
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 968768fe75286b93bf12e349a4845fdfaa1923e9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19792855"
---
# <a name="itabledata--iunknown"></a>ITableData: IUnknown

  
  
**Betrifft**: Outlook 
  
Bietet Methoden zum Arbeiten mit Tabellen. MAPI bietet Datenobjekte Tabelle oder Objekte, die **ITableData** , mit denen Dienstanbieter Tabelle Wartungen implementieren. Um ein Table-Datenobjekt zu erhalten, rufen Sie Dienstanbieter [CreateTable](createtable.md) -Funktion. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapiutil.h  <br/> |
|Verf�gbar gemacht von:  <br/> |Tabelle Datenobjekte  <br/> |
|Implementiert von:  <br/> |MAPI  <br/> |
|Aufgerufen von:  <br/> |Dienstanbieter  <br/> |
|Schnittstellenbezeichner:  <br/> |IID_IMAPITableData  <br/> |
|Zeigertyp:  <br/> |LPTABLEDATA  <br/> |
   
## <a name="vtable-order"></a>Vtable-Reihenfolge

|||
|:-----|:-----|
|[HrGetView](itabledata-hrgetview.md) <br/> |Erstellt eine Tabellenansicht, einen Zeiger auf eine Implementierung [IMAPITable](imapitableiunknown.md) zurückgibt.  <br/> |
|[HrModifyRow](itabledata-hrmodifyrow.md) <br/> |Fügt eine neue Tabellenzeile, die möglicherweise eine vorhandene Zeile ersetzen.  <br/> |
|[HrDeleteRow](itabledata-hrdeleterow.md) <br/> |Löscht eine Tabellenzeile.  <br/> |
|[HrQueryRow](itabledata-hrqueryrow.md) <br/> |Ruft eine Tabellenzeile.  <br/> |
|[HrEnumRow](itabledata-hrenumrow.md) <br/> |Ruft eine Zeile basierend auf seine Position in der Tabelle an.  <br/> |
|[HrNotify](itabledata-hrnotify.md) <br/> |Sendet eine Benachrichtigung für eine Tabellenzeile.  <br/> |
|[HrInsertRow](itabledata-hrinsertrow.md) <br/> |Eine Tabellenzeile eingefügt.  <br/> |
|[HrModifyRows](itabledata-hrmodifyrows.md) <br/> |Mehrere Tabellenzeilen, möglicherweise Ersetzen der vorhandene Zeilen eingefügt.  <br/> |
|[HrDeleteRows](itabledata-hrdeleterows.md) <br/> |Löscht mehrere Tabellenzeilen.  <br/> |
   
## <a name="remarks"></a>Hinweise

Die MAPI-Implementierung der **ITableData** arbeitet mit Tabellen halten Sie alle Daten und zugehörigen Einschränkungen im Arbeitsspeicher, leicht für die Verwendung mit sehr große Tabellen nicht geeignet. Große Einschränkungen und komplexe Vorgänge wie Kategorisierung werden nicht unterstützt. 
  
Datenobjekte Tabelle identifizieren Zeilen mithilfe von einer Indexspalte, eine Eigenschaft, die in jedem Fall ist einen eindeutigen Wert für jede Zeile. Die meisten Dienstanbieter verwenden Sie die Eigenschaft **PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) als Index-Spalte. Eigenschaften, die mehrere Werte aufweisen können nicht als eine Indexspalte verwendet werden.
  
Tabelle Datenobjekte generieren eine einzelne Benachrichtigung unabhängig von der Anzahl der Zeilen, die von einer Änderung oder Löschung betroffen sind. Wenn eine Zielzeile in einem Vorgang nicht vorhanden ist, wird eine Zeile hinzugefügt.
  
## <a name="see-also"></a>Siehe auch



[MAPI-Schnittstellen](mapi-interfaces.md)

