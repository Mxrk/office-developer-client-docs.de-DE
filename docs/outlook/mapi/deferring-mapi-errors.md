---
title: Zur�ckstellen MAPI-Fehler
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93ae6d54-41cd-433c-8124-eb07d71baa57
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: e2b091fa21dae4a1a8da23954d5f998010483da1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791507"
---
# <a name="deferring-mapi-errors"></a>Zur�ckstellen MAPI-Fehler

  
  
**Betrifft**: Outlook 
  
Einige Schnittstellenmethoden akzeptieren Sie die Kennzeichen MAPI_DEFERRED_ERRORS als Eingabeparameter. Wenn dieses Flag festgelegt ist, muss die Methode nicht sofort mit einem Wert zur�ckgegeben; Sie k�nnen den Anrufer das Ergebnis des Anrufs zu einem sp�teren Zeitpunkt wissen lassen.
  
Zur�ckstellen Fehler hilft-Dienstanbieter in ihrer Implementierung der komplexe Methoden t�tigen schneller verarbeitet. Statt viele Anforderungen zu behandeln und Zur�ckgeben eines Werts f�r die einzelnen, kann Fehler verz�gern der Anrufe f�r den Dienstanbieter geb�ndelt werden. Viele Anforderungen gleichzeitig verarbeitet senkt die Netzwerkdatenverkehr, wodurch die Leistung verbessert. Zur�ckstellen Fehler ist besonders hilfreich in Aufrufe l�schen oder Kopie-Eigenschaften, mit die Vorg�nge sehr zeitaufwendig sein k�nnen. 
  
Wenn ein Client einen Anruf ernannt werden, ohne das MAPI_DEFERRED_ERRORS-Flag festlegen, die verz�gert nur behandelt werden kann, k�nnen Dienstanbieter entweder die Fehler unabh�ngig verz�gern oder MAPI_E_TOO_COMPLEX zur�ckzugeben. Die meisten Clients sollte als Strategie vorzuziehen, dass Sie den Anruf defekt Fehler verz�gern. 
  
Die Einstellung der MAPI_DEFERRED_ERRORS �ndert Flag Implementierung des Clients Fehlerbehandlung darin, dass die zur�ckgegebene Informationen k�nnen Sie jederzeit und nicht zu einem geplanten Zeitpunkt �bermittelt werden kann. Es ist m�glich, dass ein Fehler zur�ckgegeben werden soll, wenn es zu sp�t ist nichts davon oder nachdem Daten �ber die urspr�ngliche Anforderung nicht mehr verf�gbar ist. Beispielsweise wenn ein Client **IMsgStore::OpenEntry** um einen gel�schten Ordner mit MAPI_DEFERRED_ERRORS �ffnen aufruft, wird der Client nicht des Problems wissen, bis eine **IMAPIProp::GetProps** aufgerufen wird, um eine der Eigenschaften des Ordners abzurufen. **GetProps** gibt MAPI_E_NOT_FOUND zur�ck. 
  
## <a name="see-also"></a>Siehe auch



[IMsgStore::OpenEntry](imsgstore-openentry.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)

