---
title: Lesen Sie Zeitzone Eigenschaften, ausgehend von einem Termin
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ba1b9425-6c16-cab2-da0a-a21734118098
description: In diesem Thema wird eine Funktion, ReadTimeZones, die die beiden Funktionen, BinToTZDEFINITION und BinToTZREG, lesen die Zeitzone Eigenschaften, PidLidAppointmentTimeZoneDefinitionStartDisplay und PidLidTimeZoneStruct, ausgehend von einem Termin aufruft.
ms.openlocfilehash: a344f44a1f195ec6dc5f80677f08f52be490e6b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790940"
---
# <a name="read-time-zone-properties-from-an-appointment"></a>Lesen Sie Zeitzone Eigenschaften, ausgehend von einem Termin

In diesem Thema wird eine Funktion `ReadTimeZones`, die zwei Funktionen aufruft `BinToTZDEFINITION` und `BinToTZREG`, um die Eigenschaften Zeitzone, [PidLidAppointmentTimeZoneDefinitionStartDisplay](http://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx) und [PidLidTimeZoneStruct](http://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx), ausgehend von einem Termin zu lesen.
  
**PidLidAppointmentTimeZoneDefinitionStartDisplay** enthält einen Datenstrom, der die beibehaltenen Format einer [TZDEFINITION](tzdefinition.md) Struktur zugeordnet ist, und **PidLidTimeZoneStruct** enthält einen Datenstrom, der permanente Format einer [TZREG](tzreg.md) zugeordnet ist Struktur. Die genauen Strukturen **TZDEFINITION** und **TZREG** abrufen `BinToTZDEFINITION` und `BinToTZREG` werden verwendet, um die Stream-Werte dieser Eigenschaften entsprechend zu analysieren. Diese beiden Funktionen werden in [einen Datenstrom aus eine binäre Eigenschaft zum Lesen der TZDEFINITION-Struktur zu analysieren](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md) und [einen Datenstrom aus eine binäre Eigenschaft zum Lesen der TZREG-Struktur zu analysieren](how-to-parse-a-stream-from-a-binary-property-to-read-the-tzreg-structure.md), definiert. 
  
```cpp
void ReadTimeZones(LPMAPIPROP lpAppointment) 
{ 
    HRESULT hRes = S_OK; 
    LPSPropTagArray lpNamedPropTags = NULL; 
    MAPINAMEID NamedID[2] = {0}; 
    LPMAPINAMEID lpNamedID[2]; 
    lpNamedID[0] = &amp;NamedID[0]; 
    lpNamedID[1] = &amp;NamedID[1]; 
    NamedID[0].lpguid = (LPGUID)&amp;PSETID_Appointment; 
    NamedID[0].ulKind = MNID_ID; 
    NamedID[0].Kind.lID = dispidTimeZoneStruct; 
    NamedID[1].lpguid = (LPGUID)&amp;PSETID_Appointment; 
    NamedID[1].ulKind = MNID_ID; 
    NamedID[1].Kind.lID = dispidApptTZDefStartDisplay; 
    hRes = lpAppointment->GetIDsFromNames( 
        2, 
        lpNamedID, 
        NULL, 
        &amp;lpNamedPropTags); 
    if (SUCCEEDED(hRes) &amp;&amp; lpNamedPropTags) 
    { 
        SizedSPropTagArray(2,sptaTzProps) = {2, 
            CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[0],PT_BINARY), 
            CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[1],PT_BINARY), 
        }; 
        LPSPropValue lpProps = NULL; 
        ULONG cProps = 0; 
        hRes = lpAppointment->GetProps( 
            (LPSPropTagArray)&amp;sptaTzProps, 
            NULL, 
            &amp;cProps, 
            &amp;lpProps); 
        if (SUCCEEDED(hRes) &amp;&amp; 2 == cProps &amp;&amp; lpProps) 
        { 
            if (PT_BINARY == PROP_TYPE(lpProps[0].ulPropTag)) 
            { 
                TZREG* ptzReg = BinToTZREG(lpProps[0].Value.bin.cb,lpProps[0].Value.bin.lpb); 
                // TODO: Do whatever is necessary with ptzReg. 
                delete ptzReg; 
            } 
            if (PT_BINARY == PROP_TYPE(lpProps[1].ulPropTag)) 
            { 
                TZDEFINITION* ptzDef = BinToTZDEFINITION(lpProps[1].Value.bin.cb,lpProps[1].Value.bin.lpb); 
                // TODO: Do whatever is necessary with ptzDef. 
                delete[] ptzDef; 
            } 
           } 
        MAPIFreeBuffer(lpProps); 
    } 
    MAPIFreeBuffer(lpNamedPropTags); 
}
```

## <a name="see-also"></a>Siehe auch

- [Zum neuen Basisadressen Kalender programmgesteuert Sommerzeit](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)

