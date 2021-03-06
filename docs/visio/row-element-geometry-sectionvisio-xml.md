---
title: Row-Element (Abschnitt "Geometry") ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2b273958-1997-7c63-4a61-d231f023a81f
description: Enthält Zeilen, in denen die Koordinaten der Scheitelpunkte für die Linien und Bögen, die das Shape bilden aufgeführt.
ms.openlocfilehash: 7a829651c4cab62a5c583d068211b9ffa20e725e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19797906"
---
# <a name="row-element-geometry-section-visio-xml"></a>Row-Element (Abschnitt "Geometry") ("Visio XML")

Enthält Zeilen, in denen die Koordinaten der Scheitelpunkte für die Linien und Bögen, die das Shape bilden aufgeführt.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|**Elementtyp** <br/> |[GeometryRow_Type](geometry_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Schemadatei** <br/> |VisioSchema15.xsd  <br/> |
|**Dokumentbausteine** <br/> |# .xml Master, Seite # .xml  <br/> |
   
## <a name="definition"></a>Definition

```XML
< xs:element name="Row" type="GeometryRow_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema spezifische Anforderungen, beispielsweise **Abfolge**, **MinOccurs**, **MaxOccurs**und **Wahl**, definiert finden Sie im Definitionsabschnitt. 
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[Section](section-element-sheet_type-complextypevisio-xml.md) <br/> |[Section_Type](section_type-complextypevisio-xml.md) <br/> |Enthält Zeilen, in denen die Koordinaten der Scheitelpunkte für die Linien und Bögen, die das Shape bilden aufgeführt.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

> [!NOTE]
> Das Zelle-Element ist das einzige untergeordnete Element dieses Elements. Je nach den "T"-Attribut dieses Elements die Bedeutung der Zellenelemente unterscheiden. In der folgenden Tabelle entspricht der "T"-Wert, den das Thema bezieht sich, Parathetical Text in den Namen des Elements. 
  
|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[Zellenelement (Zeile ArcTo)](arcto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten und die Krümmung eines kreisförmigen Bogens.  <br/> |
|[Zellenelement (Zeile Ellipse)](ellipse-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des Mittelpunkts der Ellipse von zwei Punkten auf der Ellipse.  <br/> |
|[Zellenelement (Zeile EllipticalArcTo)](ellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält x- und y-Koordinaten des Endpunkts eines elliptischen Bogens, X und y-Koordinaten des Steuerelements des Bogens, Winkel von der x-Achse zur größeren Achse der Ellipse und das Verhältnis zwischen der Ellipse Haupt- und Hilfsintervalle Achsen verweist.  <br/> |
|[Zellenelement (Zeile InfiniteLine)](infiniteline-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten von zwei Punkten einer unendlichen Linie.  <br/> |
|[Zellenelement (Zeile "LineTo")](lineto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält X- und y-Koordinaten des Endscheitelpunkts eines geraden Linienabschnitts.  <br/> |
|[Zellenelement (Zeilen MoveTo-Zeile)](moveto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des ersten Scheitelpunkts eines Shapes oder stellt die x- und y-Koordinaten des ersten Scheitelpunkts hinter einer Pfadlücke dar.  <br/> |
|[Zellenelement (Zeile NURBSTo)](nurbsto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten, Position des zweiten bis letzte Knoten, die Position der letzten Linienbreite, die Position des ersten Knotens, die Position der ersten Linienbreite und die Formel für ein nicht-gleichförmigen, rationalen B-Spline (NURBS).  <br/> |
|[Zellenelement (Zeile "PolylineTo")](polylineto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des letzten Punkts einer Polylinie und eine Polylinienformel.  <br/> |
|[Zellenelement (RelCubBezTo Zeile)](relcubbezto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des Endpunkts des eine kubische Bézierkurve relativ zur Höhe und Breite des Shapes, die x- und y-Koordinaten des Kontrollpunkts des Anfang des relativen Kurve-Shape Breite und Höhe und die x- und y-Koordinaten des Steuerelements Zeitpunkt des beenden, Breite und Höhe des relativen Kurve-Shapes.  <br/> |
|[Zellenelement (RelQuadBezTo Zeile)](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des Endpunkts des eine quadratische Bézier-Kurve relativ zur Höhe und Breite des Shapes und die x- und y-Koordinaten des Kontrollpunkts Breite und Höhe des relativen Kurve-Shapes.  <br/> |
|[Zellenelement (RelEllipticalArcTo Zeile)](relellipticalarcto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |X- und y-Koordinaten des Endpunkts der eines elliptischen Bogens relativ zur Höhe und Breite des Shapes, X und y-Koordinaten der Kontrollpunkte des Bogens relativ zu der Breite des Shapes und Height, Winkel zwischen der x-Achse zur größeren Achse der Ellipse und das Verhältnis zwischen enthält der Ellipse Haupt- und Hilfsintervalle Achsen.  <br/> |
|[Zellenelement (RelLineTo Zeile)](rellineto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält X- und y-Koordinaten des Endscheitelpunkts eines geraden Linienabschnitts relativ zur Breite und Höhe des Shapes.  <br/> |
|[Zellenelement (RelMoveTo Zeile)](relmoveto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des ersten Scheitelpunkts eines Shapes oder die x- und y-Koordinaten des ersten Scheitelpunkts hinter einer Pfadlücke in einem Pfad, relativ zur Höhe und Breite der Form.  <br/> |
|[Zellenelement (RelQuadBezTo Zeile)](relquadbezto-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten des Endpunkts des eine quadratische Bézier-Kurve relativ zur Höhe und Breite des Shapes und die x- und y-Koordinaten des Kontrollpunkts Breite und Höhe des relativen Kurve-Shapes.  <br/> |
|[Zellenelement (Zeile "SplineKnot")](splineknot-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten für den Kontrollpunkt eines Splines und den Knoten eines Splines.  <br/> |
|[Zellenelement (Zeile SplineStart)](splinestart-row-geometry-section.md) <br/> |[Cell_Type](http://msdn.microsoft.com/library/6f23bcc4-af93-4023-a380-3e78a228e166%28Office.15%29.aspx) <br/> |Enthält die x- und y-Koordinaten für den zweiten Kontrollpunkts eines Splines, dessen zweiten Knoten, dessen ersten Knoten, der letzte Knoten und den Grad eines Splines.  <br/> |
   
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|ENTF  <br/> |XSD: Boolean  <br/> |Optional  <br/> |Gibt an, ob eine Zeile, die von einem master-Shape andernfalls geerbt werden würden gelöscht wurde.  <br/> |Werte des Typs xsd: Boolean.  <br/> |
|IX  <br/> |XSD:unsignedInt  <br/> |Optional  <br/> |Gibt den Bezeichner eins für die Zeile. Es sollte eindeutigen sein und andere Bezeichner im gleichen Abschnitt größer. Das Attribut IX wird nur für die Zeichen, Verbindung, Feld, FillGradient, Geometrie, Layer, LineGradient, Absatz, Reviewer, neu und Registerkarten Abschnitte verwendet. Eine Zeile können Sie nur die Attribute IX oder N haben.  <br/> |Werte des Typs Xsd:unsignedInt.  <br/> |
|LocalName  <br/> |XSD: String  <br/> |Optional  <br/> |Gibt den eindeutigen Namen der Sprache ab der Zeile an.  <br/> |Werte des Typs xsd: String.  <br/> |
|N  <br/> |XSD: String  <br/> |Optional  <br/> |Gibt die eindeutige sprachenunabhängige Name der Zeile an. Das N-Attribut wird nur für die Benutzer, Eigenschaften-, Aktionen, Steuerelement, Verbindung, Hyperlink und ActionTag Abschnitte verwendet. Eine Zeile können Sie nur die Attribute IX oder N haben.  <br/> |Werte des Typs xsd: String.  <br/> |
|T  <br/> |XSD: String  <br/> |Optional  <br/> |Gibt den Typ des geometrischen Pfads dargestellt durch die Zeile und in Geometrie Visualisierung verwendet. Das T-Attribut wird nur für den Abschnitt "Geometry" verwendet.  <br/> |Werte des Typs xsd: String.  <br/> |
   
## <a name="remarks"></a>Hinweise

Das Attribut **T** dieses Elements **Zeile** muss eine der eine begrenzte Auswahl von Werten sein, die ShapeSheet-Zeilen entsprechen. Finden Sie in der Tabelle unten, um die Werte des Attributs **T** zu bestimmen, die für dieses Element **Zeile** zulässig sind. 
  
|**Wert**|**Beschreibung**|**Weitere Informationen**|
|:-----|:-----|:-----|
|ArcTo  <br/> |Enthält die x- und y-Koordinaten und die Krümmung eines kreisförmigen Bogens.  <br/> |[Zeile "ArcTo" (Abschnitt "Geometry")](arcto-row-geometry-section.md) <br/> |
|Ellipse  <br/> |Enthält die x- und y-Koordinaten des Mittelpunkts der Ellipse von zwei Punkten auf der Ellipse.  <br/> |[Zeile "Ellipse" (Abschnitt "Geometry")](ellipse-row-geometry-section.md) <br/> |
|EllipticalArcTo  <br/> |Enthält x- und y-Koordinaten des Endpunkts eines elliptischen Bogens, X und y-Koordinaten des Steuerelements des Bogens, Winkel von der x-Achse zur größeren Achse der Ellipse und das Verhältnis zwischen der Ellipse Haupt- und Hilfsintervalle Achsen verweist.  <br/> |[Zeile "EllipticalArcTo" (Abschnitt "Geometry")](ellipticalarcto-row-geometry-section.md) <br/> |
|InfiniteLine  <br/> |Enthält die x- und y-Koordinaten von zwei Punkten einer unendlichen Linie.  <br/> |[Zeile "InfiniteLine" (Abschnitt "Geometry")](http://msdn.microsoft.com/library/Contains the x- and y-coordinates of two points on an infinite line.%28Office.15%29.aspx) <br/> |
|LineTo  <br/> |Enthält X- und y-Koordinaten des Endscheitelpunkts eines geraden Linienabschnitts.  <br/> |[Zeile "LineTo" (Abschnitt "Geometry")](lineto-row-geometry-section.md) <br/> |
|MoveTo  <br/> |Enthält die x- und y-Koordinaten des ersten Scheitelpunkts eines Shapes oder stellt die x- und y-Koordinaten des ersten Scheitelpunkts hinter einer Pfadlücke dar.  <br/> |[Zeile "MoveTo" (Abschnitt "Geometry")](moveto-row-geometry-section.md) <br/> |
|NURBSTo  <br/> |Enthält die x- und y-Koordinaten, Position des zweiten bis letzte Knoten, die Position der letzten Linienbreite, die Position des ersten Knotens, die Position der ersten Linienbreite und die Formel für ein nicht-gleichförmigen, rationalen B-Spline (NURBS).  <br/> |[Zeile "NURBSTo" (Abschnitt "Geometry")](nurbsto-row-geometry-section.md) <br/> |
|PolylineTo  <br/> |Enthält die x- und y-Koordinaten des letzten Punkts einer Polylinie und eine Polylinienformel.  <br/> |[Zeile "PolylineTo" (Abschnitt "Geometry")](polylineto-row-geometry-section.md) <br/> |
|RelCubBezTo  <br/> |Enthält die x- und y-Koordinaten des Endpunkts des eine kubische Bézierkurve relativ zur Höhe und Breite des Shapes, die x- und y-Koordinaten des Kontrollpunkts des Anfang des relativen Kurve-Shape Breite und Höhe und die x- und y-Koordinaten des Steuerelements Zeitpunkt des beenden, Breite und Höhe des relativen Kurve-Shapes.  <br/> |[RelCubBezTo Zeile (Abschnitt "Geometry")](relcubbezto-row-geometry-section.md) <br/> |
|RelEllipticalArcTo  <br/> |X- und y-Koordinaten des Endpunkts der eines elliptischen Bogens relativ zur Höhe und Breite des Shapes, X und y-Koordinaten der Kontrollpunkte des Bogens relativ zu der Breite des Shapes und Height, Winkel zwischen der x-Achse zur größeren Achse der Ellipse und das Verhältnis zwischen enthält der Ellipse Haupt- und Hilfsintervalle Achsen.  <br/> |[RelEllipticalArcTo Zeile (Abschnitt "Geometry")](relellipticalarcto-row-geometry-section.md) <br/> |
|RelLineTo  <br/> |Enthält X- und y-Koordinaten des Endscheitelpunkts eines geraden Linienabschnitts relativ zur Breite und Höhe des Shapes.  <br/> |[RelLineTo Zeile (Abschnitt "Geometry")](rellineto-row-geometry-section.md) <br/> |
|RelMoveTo  <br/> |Enthält die x- und y-Koordinaten des ersten Scheitelpunkts eines Shapes oder die x- und y-Koordinaten des ersten Scheitelpunkts hinter einer Pfadlücke in einem Pfad, relativ zur Höhe und Breite der Form.  <br/> |[RelMoveTo Zeile (Abschnitt "Geometry")](relmoveto-row-geometry-section.md) <br/> |
|RelQuadBezTo  <br/> |Enthält die x- und y-Koordinaten des Endpunkts des eine quadratische Bézier-Kurve relativ zur Höhe und Breite des Shapes und die x- und y-Koordinaten des Kontrollpunkts Breite und Höhe des relativen Kurve-Shapes.  <br/> |[RelQuadBezTo Zeile (Abschnitt "Geometry")](relquadbezto-row-geometry-section.md) <br/> |
|SplineKnot  <br/> |Enthält die x- und y-Koordinaten für den Kontrollpunkt eines Splines und den Knoten eines Splines.  <br/> |[Zeile "SplineKnot" (Abschnitt "Geometry")](splineknot-row-geometry-section.md) <br/> |
|SplineStart  <br/> |Enthält die x- und y-Koordinaten für den zweiten Kontrollpunkts eines Splines, dessen zweiten Knoten, dessen ersten Knoten, der letzte Knoten und den Grad eines Splines.  <br/> |[Zeile "SplineStart" (Abschnitt "Geometry")](splinestart-row-geometry-section.md) <br/> |
   

