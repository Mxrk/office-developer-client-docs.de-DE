---
title: SectionDef_Type ComplexType ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ab57bf2-0d9f-4a3a-4882-c77d7c781cbd
ms.openlocfilehash: 426e62ea7a9f990555776e3ac732dd43e614582d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797985"
---
# <a name="sectiondeftype-complextype-visio-xml"></a>SectionDef_Type ComplexType ("Visio XML")

## <a name="type-information"></a>Informationen zum Typ

|||
|:-----|:-----|
|**Namespace** <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|**Schemadatei** <br/> |VisioSchema15-2012-06-05.xsd  <br/> |
|**Erweiterungsbasis** <br/> |Keine  <br/> |
   
## <a name="definition"></a>Definition

```XML
          <xs:complexType name="SectionDef_Type">
          
          <xs:sequence>
    <xs:element name="CellDef"  type="CellDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="RowDef"  type="RowDef_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="T"
  type="xsd:string"
    />
    <xs:attribute name="S"
  type="xsd:unsignedByte"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema spezifische Anforderungen, beispielsweise **Abfolge**, **MinOccurs**, **MaxOccurs**und **Wahl**, definiert finden Sie im Definitionsabschnitt. 
  
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[CellDef](http://msdn.microsoft.com/library/f0ec7afe-9e0a-b5e5-82dd-4adff1c1607f%28Office.15%29.aspx) <br/> |[CellDef_Type](celldef_type-complextypevisio-xml.md) <br/> ||
|[RowDef](http://msdn.microsoft.com/library/25615be9-1d19-1ba9-4192-7d4a0dfae717%28Office.15%29.aspx) <br/> |[RowDef_Type](rowdef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|N  <br/> |XSD: String  <br/> |erforderlich  <br/> ||Werte des Typs xsd: String.  <br/> |
|S  <br/> |XSD:unsignedByte  <br/> |Optional  <br/> ||Werte des Typs Xsd:unsignedByte.  <br/> |
|T  <br/> |XSD: String  <br/> |Optional  <br/> ||Werte des Typs xsd: String.  <br/> |
   

