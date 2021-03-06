---
title: Component Object Model und MAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cca4c70d-b73a-4834-80b5-9cb5889f63cc
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: cf687a7bfadb0981ca3440c2f81bc5de8f910924
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791443"
---
# <a name="component-object-model-and-mapi"></a>Component Object Model und MAPI

  
  
**Betrifft**: Outlook 
  
Die Windows SDK-Dokumentation umfasst eine umfassende Erläuterung der Regeln für die Implementierung von Objekten, die an Component Object Model (COM) entsprechen. Diese Regeln behandelt, wie Sie die folgenden Aufgaben ausführen:
  
- Entwerfen von Schnittstellen und Objekte.
    
- Implementieren Sie die [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx) -Schnittstelle. 
    
- Arbeitsspeicher verwaltet werden.
    
- Behandeln Sie Referenzzähler.
    
- Implementieren des Apartmentthreading-Thread-Objekte.
    
Auch wenn alle Objekte der MAPI-COM-basierte betrachtet werden, da diese Schnittstellen implementieren, die von [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28VS.85%29.aspx)erben, weicht MAPI in manchen Fällen von den standard-COM-Regeln ab. Diese Abweichung kann Entwickler mehr Flexibilität, in deren Implementierung. Beispielsweise beschreibt eine MAPI-Schnittstelle wie jede COM-Schnittstelle, einen Vertrag zwischen Implementierer und des Anrufers. Nachdem die Schnittstelle erstellt und veröffentlicht wird, dessen Definition kann nicht und wird nicht geändert. MAPI Featureordner nicht auf diese Beschreibung, aber es etwas lockert die Beschreibung. Implementierer können keine bestimmte Methoden implementiert einen der folgenden Fehlerwerte an den Anrufer zurückgeben: 
  
- MAPI_E_NO_SUPPORT
    
- MAPI_E_TOO_COMPLEX
    
- MAPI_E_BAD_CHARWIDTH
    
- MAPI_E_TYPE_NO_SUPPORT
    
Die anderen Abweichung von den standard-COM-Regeln werden in der folgenden Tabelle beschrieben.
  
|**COM-Programmierung Regel**|**MAPI-Variante**|
|:-----|:-----|
|Alle Parameter in Schnittstellenmethoden sollte Unicode sein.  <br/> |MAPI-Schnittstellen sind definiert, um Unicode- oder ANSI-Parameter zu ermöglichen. Außerdem müssen viele Methoden, die einen Zeichenfolgenparameter haben einen Parameter **UlFlags** ; die Breite eines Parameters wird durch den Wert der die Option MAPI_UNICODE in **UlFlags**angezeigt. Einige MAPI-Schnittstellen nicht unterstützen Unicode und MAPI_E_BAD_CHARWIDTH zurück, wenn die Option MAPI_UNICODE festgelegt ist.  <br/> |
|Alle Schnittstellenmethoden sollte den Rückgabetyp HRESULT verfügen.  <br/> |MAPI hat mindestens eine Methode, die einen nicht-HRESULT-Wert zurückgibt: [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md).  <br/> |
|Anrufer und -Implementierer sollte reservieren und Speicher für die Parameter für die Benutzeroberfläche mithilfe der standardmäßigen COM-Aufgabe Allocators freigeben.  <br/> |Alle MAPI-Methoden mit der verknüpften Allocators [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md)und [MAPIFreeBuffer](mapifreebuffer.md) können Speicher für die Parameter für die Benutzeroberfläche verwalten. Alle MAPI-Implementierungen von OLE, wie etwa [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx), definierten Schnittstellen verwenden Sie die standardmäßigen COM-Aufgabe Allocators.  <br/> |
|Zeigerparameter müssen ganz hin explizit auf NULL festgelegt werden, wenn eine Methode fehlschlägt.  <br/> |MAPI-Schnittstellen erfordern, dass out-Zeigerparameter, die entweder werden auf NULL festgelegt wurde, oder bleiben unverändert, wenn eine Methode, ein Fehler auftritt. Legen Sie alle MAPI-Implementierungen von OLE explizit definierten Schnittstellen out-Parameter auf NULL bei einem Fehler.  <br/> |
|Implementieren einer aggregierbaren Objekte nach Möglichkeit.  <br/> |MAPI-Schnittstellen sind nicht aggregierbaren.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)


[MAPI-Objekt und Übersicht über die Benutzeroberfläche](mapi-object-and-interface-overview.md)

