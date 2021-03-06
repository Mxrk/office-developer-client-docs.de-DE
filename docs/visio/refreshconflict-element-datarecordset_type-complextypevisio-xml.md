---
title: RefreshConflict-Element (DataRecordSet_Type ComplexType) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 373983f7-fc0c-95f6-7665-7ed47de82e5e
description: Gibt eine Zeile im Datenrecordset verknüpft ein Shape, das nach der Datenrecordsets ein Konflikt vorliegt.
ms.openlocfilehash: 0bcfb38c1a9ef84fc8581476fcce13b0de32c308
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797793"
---
# <a name="refreshconflict-element-datarecordsettype-complextype-visio-xml"></a>RefreshConflict-Element (DataRecordSet_Type ComplexType) ("Visio XML")

Gibt eine Zeile im Datenrecordset verknüpft ein Shape, das nach der Datenrecordsets ein Konflikt vorliegt.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|**Elementtyp** <br/> |[RefreshConflict_Type](refreshconflict_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Schemadatei** <br/> |VisioSchema15.xsd  <br/> |
|**Dokumentbausteine** <br/> |Recordsets.Xml  <br/> |
   
## <a name="definition"></a>Definition

```XML
< xs:element name="RefreshConflict" type="RefreshConflict_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element>
```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema spezifische Anforderungen, beispielsweise **Abfolge**, **MinOccurs**, **MaxOccurs**und **Wahl**, definiert finden Sie im Definitionsabschnitt. 
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[DataRecordSet](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[DataRecordSet_Type](datarecordset_type-complextypevisio-xml.md) <br/> |Speichert, formatiert und aktualisiert Daten, die aus einer Datenbank in Microsoft Visio abgefragt wurden, und zeigt diese Daten an.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

Keine.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|PageID  <br/> |XSD:unsignedInt  <br/> |erforderlich  <br/> |Seiten-ID der Form, die den Konflikt beteiligt.  <br/> |Werte des Typs Xsd:unsignedInt.  <br/> |
|RowID  <br/> |XSD:unsignedInt  <br/> |erforderlich  <br/> |Die ursprünglichen Zeilen-ID der Zeile jetzt in Konflikt nachdem Daten aktualisiert wurde.  <br/> |Werte des Typs Xsd:unsignedInt.  <br/> |
|ShapeID  <br/> |XSD:unsignedInt  <br/> |erforderlich  <br/> |Shape-ID der Form, die den Konflikt beteiligt.  <br/> |Werte des Typs Xsd:unsignedInt.  <br/> |
   

