---
title: WrapCompressedRTFStreamEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 45abee1c-d7fb-b0f9-522d-8ba34caf1094
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: bdb879a2412c817b7b314cd7bf6de1fa4c9f40d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795851"
---
# <a name="wrapcompressedrtfstreamex"></a>WrapCompressedRTFStreamEx

**Betrifft**: Outlook 
  
Dekomprimiert die der Textkörper einer e-Mail-Nachricht, die im komprimierten Rich Text Format (RTF), gibt das Format an den dekomprimierten Stream-Objekts, optional konvertiert den dekomprimierten Datenstrom in seinem nativen Format und gibt entweder den dekomprimierten Stream oder die systemeigene Datenstrom konvertiert.
  
## <a name="quick-info"></a>QuickInfo

|||
|:-----|:-----|
|Vom exportiert werden:  <br/> |Msmapi32.dll  <br/> |
|Aufgerufen von:  <br/> |Client  <br/> |
|Implementiert von:  <br/> |Outlook  <br/> |
   
```cpp
HRESULT __stdcall WrapCompressedRTFStreamEx( 
    LPSTREAM            lpCompressedRTFStream, 
    CONST RTF_WCSINFO   *pWCSInfo, 
    LPSTREAM            *lppUncompressedRTFStream, 
    RTF_WCSRETINFO      *pRetInfo); 

```

## <a name="parameters"></a>Parameter

_lpCompressedRTFStream_
  
> [in] Dies ist ein Zeiger auf ein Datenstrom, der für die [Kanonische PidTagRtfCompressed-Eigenschaft](pidtagrtfcompressed-canonical-property.md) einer Nachricht geöffnet wird. 
    
_pWCSInfo_
  
> [in] Hierbei handelt es sich um einen Zeiger auf eine 
    
   [RTF_WCSINFO](rtf_wcsinfo.md) -Struktur, die Optionen für die Funktion enthält. 
    
_lppUncompressedRTFStream_
  
> [out] Dies ist ein Zeiger auf den Speicherort, an ein Stream für die dekomprimierten RTF zurückgegeben wird. 
    
_pRetInfo_
  
> [out] Dies ist ein Zeiger auf eine [RTF_WCSRETINFO](rtf_wcsretinfo.md) -Struktur, die Informationen zum Format der zurückgegebenen dekomprimierten Stream-Objekts enthält. 
    
## <a name="return-values"></a>Rückgabewerte

S_OK 
  
- Der Funktionsaufruf ist erfolgreich.
    
MAPI_E_INVALID_PARAMETER 
  
- Dies wird zurückgegeben, wenn das Flag **MAPI_NATIVE_BODY** mit dem **MAPI_MODIFY** -Flag im Feld **UlFlags** der Struktur **RTF_WCSINFO** an, auf das *pWCSInfo* zeigt kombiniert ist. 
    
## <a name="remarks"></a>Hinweise

**WrapCompressedRTFStreamEx** ermöglicht den Zugriff auf den Textkörper einer e-Mail-Nachricht in komprimierten RTF Dekomprimieren des Streams gekapselten der dekomprimierten Stream und das Format und optional die systemeigene Textstream zurückgegeben. Die systemeigene Textstream kann in RTF, nur-Text oder HTML sein. 
  
Microsoft Office Outlook-Objektmodell enthält eine **Body** -Eigenschaft für **MailItem** -Objekten und einer [Der MailItem.BodyFormat-Eigenschaft (Outlook)](http://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx) , der das Format des Textkörpers angibt. Entwurfsbedingt Ruft eine Lösung, die von Outlook nicht vertrauenswürdig ist Sicherheit Dialogfelder von Outlook-Sicherheitspersonals generiert. Verwenden der exportierten MAPI-Funktion **WrapCompressedRTFStreamEx** ermöglicht eine Lösung für MAPI anstelle von Outlook-Objektmodell verwenden und diese Sicherheitsdialogfelder zu vermeiden. 
  
Da die **MAPI\_NATIVE_BODY** Flag kombiniert werden die **MAPI\_ändern** -Kennzeichen in das Feld **UlFlags** von der **RTF\_WCSINFO** Struktur an, auf zeigt *pWCSInfo*, Sie können nur zugreifen, die systemeigene Textkörper-Datenstrom im schreibgeschützten Modus. Um die systemeigene Textstream im Lese-/Schreibmodus zuzugreifen, sollten Sie die **WrapCompressedRTFStream** -Funktion verwenden. 
  
## <a name="see-also"></a>Siehe auch

- [Abrufen von den Textkörper einer Nachricht im RTF komprimierte und konvertieren Sie es in seinem nativen Format](how-to-retrieve-the-body-of-a-message-in-compressed-rtf-and-convert.md)

