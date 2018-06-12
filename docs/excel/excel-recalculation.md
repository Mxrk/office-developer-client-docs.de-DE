---
title: Excel-Neuberechnung
manager: kelbow
ms.date: 03/09/2018
ms.audience: Developer
ms.topic: overview
keywords:
- forced calculation [excel 2007],selective recalculation [Excel 2007],functions [Excel 2007], volatile,calculation modes,recalculated cells [Excel 2007],dependence [Excel 2007],specified worksheet calculation [Excel 2007],recalculation [Excel 2007],workbook tree rebuild [Excel 2007],range calculation [Excel 2007],Excel recalculation,volatile functions [Excel 2007],functions [Excel 2007], non-volatile,active worksheet calculation [Excel 2007],dirty cells [Excel 2007],non-volatile functions [Excel 2007],forced recalculation [Excel 2007]
localization_priority: Normal
ms.assetid: b4c38442-42e6-4fd2-a1b0-97cfa3300379
description: 'Gilt f�r: Excel 2013�| Office 2013�| Visual Studio'
ms.openlocfilehash: 9964f2c4282158e83891d82ba43fa19f23ab1eb6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790467"
---
# <a name="excel-recalculation"></a><span data-ttu-id="caa1f-104">Excel-Neuberechnung</span><span class="sxs-lookup"><span data-stu-id="caa1f-104">Excel Recalculation</span></span>

 <span data-ttu-id="caa1f-105">**Gilt für**: Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="caa1f-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="caa1f-106">Eine Neuberechnung kann in Microsoft Excel auf verschiedene Weisen ausgel�st werden, beispielsweise durch folgende Aktionen:</span><span class="sxs-lookup"><span data-stu-id="caa1f-106">The user can trigger recalculation in Microsoft Excel in several ways, for example:</span></span>
  
- <span data-ttu-id="caa1f-107">Eingeben neuer Daten (wenn Excel sich im automatischen Neuberechnungsmodus befindet, siehe Beschreibung weiter unten in diesem Thema)</span><span class="sxs-lookup"><span data-stu-id="caa1f-107">Entering new data (if Excel is in Automatic recalculation mode, described later in this topic).</span></span>
    
- <span data-ttu-id="caa1f-108">Ausgeben der expliziten Anweisung, dass Excel eine Arbeitsmappe ganz oder teilweise neu berechnen soll</span><span class="sxs-lookup"><span data-stu-id="caa1f-108">Explicitly instructing Excel to recalculate all or part of a workbook.</span></span>
    
- <span data-ttu-id="caa1f-109">L�schen oder Einf�gen einer Zeile oder Spalte</span><span class="sxs-lookup"><span data-stu-id="caa1f-109">Deleting or inserting a row or column.</span></span>
    
- <span data-ttu-id="caa1f-110">Speichern einer Arbeitsmappe bei aktivierter Option **Vor dem Speichern neu berechnen**</span><span class="sxs-lookup"><span data-stu-id="caa1f-110">Saving a workbook while the **Recalculate before save** option is set.</span></span> 
    
- <span data-ttu-id="caa1f-111">Durchf�hren bestimmter Autofilter-Aktionen</span><span class="sxs-lookup"><span data-stu-id="caa1f-111">Performing certain Autofilter actions.</span></span>
    
- <span data-ttu-id="caa1f-112">Doppelklicken auf eine Zeilen- oder Spaltentrennlinie (im automatischen Berechnungsmodus)</span><span class="sxs-lookup"><span data-stu-id="caa1f-112">Double-clicking a row or column divider (in Automatic calculation mode).</span></span>
    
- <span data-ttu-id="caa1f-113">Hinzuf�gen, Bearbeiten oder L�schen eines definierten Namens</span><span class="sxs-lookup"><span data-stu-id="caa1f-113">Adding, editing, or deleting a defined name.</span></span>
    
- <span data-ttu-id="caa1f-114">Umbenennen eines Arbeitsblatts</span><span class="sxs-lookup"><span data-stu-id="caa1f-114">Renaming a worksheet.</span></span>
    
- <span data-ttu-id="caa1f-115">�ndern der Position eines Arbeitsblatts in Bezug auf andere Arbeitsbl�tter</span><span class="sxs-lookup"><span data-stu-id="caa1f-115">Changing the position of a worksheet in relation to other worksheets.</span></span>
    
- <span data-ttu-id="caa1f-116">Ausblenden oder Einblenden von Zeilen, nicht aber Spalten</span><span class="sxs-lookup"><span data-stu-id="caa1f-116">Hiding or unhiding rows, but not columns.</span></span>
    
> [!NOTE]
> <span data-ttu-id="caa1f-p101">[!HINWEIS] In diesem Thema wird kein Unterschied dazwischen gemacht, ob der Benutzer direkt eine Taste dr�ckt oder mit der Maus klickt und ob die entsprechenden Aufgaben von einem Befehl oder einem Makro ausgef�hrt werden. Der Benutzer f�hrt den Befehl aus oder veranlasst die Ausf�hrung des Befehls durch eine Aktion, sodass dies als Benutzeraktion angesehen wird. Daher bedeutet bedeutet der Ausdruck "der Benutzer": "der Benutzer oder ein vom Benutzer gestarteter Befehl oder Prozess".</span><span class="sxs-lookup"><span data-stu-id="caa1f-p101">This topic does not distinguish between the user directly pressing a key or clicking the mouse, and those tasks being done by a command or macro. The user runs the command, or does something to cause the command to run so that it is still considered a user action. Therefore the phrase "the user" also means "the user, or a command or process started by the user."</span></span> 
  
## <a name="dependence-dirty-cells-and-recalculated-cells"></a><span data-ttu-id="caa1f-120">Abh�ngigkeit, ge�nderte Zellen und neu berechnete Zellen</span><span class="sxs-lookup"><span data-stu-id="caa1f-120">Dependence, Dirty Cells, and Recalculated Cells</span></span>

<span data-ttu-id="caa1f-121">Die Berechnung von Arbeitsbl�ttern in Excel kann als dreistufiger Prozess betrachtet werden:</span><span class="sxs-lookup"><span data-stu-id="caa1f-121">The calculation of worksheets in Excel can be viewed as a three-stage process:</span></span>
  
1. <span data-ttu-id="caa1f-122">Erstellen einer Abh�ngigkeitsstruktur</span><span class="sxs-lookup"><span data-stu-id="caa1f-122">Construction of a dependency tree</span></span>
    
2. <span data-ttu-id="caa1f-123">Erstellen einer Berechnungskette</span><span class="sxs-lookup"><span data-stu-id="caa1f-123">Construction of a calculation chain</span></span>
    
3. <span data-ttu-id="caa1f-124">Neuberechnen von Zellen</span><span class="sxs-lookup"><span data-stu-id="caa1f-124">Recalculation of cells</span></span>
    
<span data-ttu-id="caa1f-p102">Die Abh�ngigkeitsstruktur informiert Excel dar�ber, welche Zellen von anderen abh�ngen, bzw. welche Zellen Vorg�nger von anderen sind. Aus dieser Struktur erstellt Excel eine Berechnungskette. Die Berechnungskette listet alle Zellen mit Formeln in der Reihenfolge auf, in der sie berechnet werden sollen. W�hrend der Neuberechnung �berarbeitet Excel diese Kette, wenn eine Formel gefunden wird, die von einer noch nicht berechneten Zelle abh�ngt. In diesem Fall werden die Zelle, die gerade berechnet wird, und die davon abh�ngigen Zellen in der Kette nach unten verschoben. Aus diesem Grund k�nnen Berechnungszeiten in einem Arbeitsblatt, das gerade erst ge�ffnet wurde, h�ufig in den ersten paar Berechnungszyklen verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p102">The dependency tree informs Excel about which cells depend on which others, or equivalently, which cells are precedents for which others. From this tree, Excel constructs a calculation chain. The calculation chain lists all the cells that contain formulas in the order in which they should be calculated. During recalculation, Excel revises this chain if it comes across a formula that depends on a cell that has not yet been calculated. In this case, the cell that is being calculated and its dependents are moved down the chain. For this reason, calculation times can often improve in a worksheet that has just been opened in the first few calculation cycles.</span></span>
  
<span data-ttu-id="caa1f-p103">Wenn eine �nderung an der Struktur einer Arbeitsmappe vorgenommen wird (z. B. durch Eingabe einer neuen Formel), erstellt Excel die Abh�ngigkeitsstruktur und die Berechnungskette neu. Wenn neue Daten oder neue Formeln eingegeben werden, markiert Excel alle Zellen, die von den neuen Daten abh�ngen, als Zellen, f�r die eine Neuberechnung erforderlich ist. Auf diese Weise markierte Zellen werden als  *ge�ndert*  bezeichnet. Alle direkt und indirekt abh�ngigen Zellen werden als ge�ndert markiert; dies bedeutet Folgendes: Wenn B1 von A1 und C1 von B1 abh�ngt, werden bei einer �nderung von A1 sowohl B1 als auch C1 als ge�ndert markiert.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p103">When a structural change is made to a workbook, for example, when a new formula is entered, Excel reconstructs the dependency tree and calculation chain. When new data or new formulas are entered, Excel marks all the cells that depend on that new data as needing recalculation. Cells that are marked in this way are known as  *dirty*  . All direct and indirect dependents are marked as dirty so that if B1 depends on A1, and C1 depends on B1, when A1 is changed, both B1 and C1 are marked as dirty.</span></span> 
  
<span data-ttu-id="caa1f-p104">Wenn eine Zelle direkt oder indirekt von sich selbst abh�ngt, erkennt Excel den Zirkelbezug und gibt eine Warnung aus. Dies ist normalerweise eine Fehlerbedingung, die der Benutzer beheben muss, und Excel zeigt sehr hilfreiche grafische und Navigationstools an, die den Benutzer bei der Suche nach dem Ursprung des Zirkelbezugs unterst�tzen. In einigen F�llen ist diese Bedingung sogar w�nschenswert, z.�B. wenn Sie eine iterative Berechnung durchf�hren m�chten, bei der der Startpunkt der jeweils n�chsten Iteration das Ergebnis der vorherigen Iteration ist. Excel unterst�tzt die Steuerung von iterativen Berechnungen �ber das Dialogfeld mit Berechnungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p104">If a cell depends, directly or indirectly, on itself, Excel detects the circular reference and warns the user. This is usually an error condition that the user must fix, and Excel provides very helpful graphical and navigational tools to help the user to find the source of the circular dependency. In some cases, you might deliberately want this condition to exist. For example, you might want to run an iterative calculation where the starting point for the next iteration is the result of the previous iteration. Excel supports control of iterative calculations through the calculation options dialog box.</span></span>
  
<span data-ttu-id="caa1f-p105">Nachdem Zellen als ge�ndert markiert wurden, wird bei der n�chsten Neuberechnung der Inhalt jeder ge�nderten Zelle von Excel erneut ausgewertet, und zwar in der von der Berechnungskette vorgegebenen Reihenfolge. F�r das vorherige Beispiel bedeutet dies, dass zuerst B1 und dann C1 ausgewertet wird. Diese Neuberechnung findet im automatischen Neuberechnungsmodus unmittelbar nach dem Markieren der Zellen als ge�ndert statt, andernfalls erst sp�ter.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p105">After marking cells as dirty, when a recalculation is next done, Excel reevaluates the contents of each dirty cell in the order dictated by the calculation chain. In the example given earlier, this means B1 is first, and then C1. This recalculation occurs immediately after Excel finishes marking cells as dirty if the recalculation mode is automatic; otherwise, it occurs later.</span></span>
  
<span data-ttu-id="caa1f-p106">Ab Microsoft Excel 2002 unterst�tzt das **Range**-Objekt in Microsoft Visual Basic for Applications (VBA) die **Range.Dirty**-Methode, die Zellen mit der Markierung versieht, dass eine Berechung erforderlich ist. Wenn diese Methode zusammen mit der **Range.Calculate**-Methode verwendet wird (siehe n�chster Abschnitt), wird die erzwungene Neuberechnung von Zellen in einem angegebenen Bereich aktiviert. Dies ist bei der Durchf�hrung einer eingeschr�nkten Berechnung im manuellen Berechnungsmodus w�hrend eines Makros hilfreich, um zu vermeiden, dass unn�tigerweise Zellen berechnet werden, die nicht mit der Makrofunktion in Zusammenhang stehen. Berechnungsmethoden f�r Bereiche stehen in der C-API nicht zur Verf�gung.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p106">Starting in Microsoft Excel 2002, the **Range** object in Microsoft Visual Basic for Applications (VBA) supports a method, **Range.Dirty**, which marks cells as needing calculation. When it is used together with the **Range.Calculate** method (see next section), it enables forced recalculation of cells in a given range. This is useful when you are performing a limited calculation during a macro, where the calculation mode is set to manual, to avoid the overhead of calculating cells unrelated to the macro function. Range calculation methods are not available through the C API.</span></span> 
  
<span data-ttu-id="caa1f-p107">In Excel 2002 und fr�heren Versionen wurde von Excel f�r jedes Arbeitsblatt in jeder ge�ffneten Arbeitsmappe eine Berechnungskette erstellt. Dies f�hrte dazu, dass die Verarbeitung von Verkn�pfungen zwischen Arbeitsbl�ttern ziemlich kompliziert war, und erforderte einige Sorgfalt, um eine effiziente Neuberechnung sicherzustellen. Insbesondere sollten Sie in Excel 2000 arbeitsblatt�bergreifende Abh�ngigkeiten m�glichst vermeiden und Arbeitsbl�tter in alphabetischer Reihenfolge benennen, sodass Arbeitsbl�tter, die von anderen Arbeitsbl�ttern abh�ngig sind, alphabetisch nach den Arbeitsbl�ttern kommen, von denen sie abh�ngen.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p107">In Excel 2002 and earlier versions, Excel built a calculation chain for each worksheet in each open workbook. This resulted in some complexity in the way links between worksheets were handled, and required some care to ensure efficient recalculation. In particular, in Excel 2000, you should minimize cross-worksheet dependencies and name worksheets in alphabetical order so that sheets that depend on other sheets come alphabetically after the sheets they depend on.</span></span>
  
<span data-ttu-id="caa1f-p108">In Excel 2007 wurde die Logik verbessert und erm�glicht die Neuberechnung in mehreren Threads, sodass Abschnitte der Berechnungskette nicht voneinander abh�ngig sind und gleichzeitig berechnet werden k�nnen. Sie k�nnen Excel so konfigurieren, dass mehrere Threads auf einem Computer mit einem einzelnen Prozessor verwendet werden, oder dass ein einzelner Thread auf einem Computer mit mehreren Prozessoren oder Prozessorkernen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p108">In Excel 2007, the logic was improved to enable recalculation on multiple threads so that sections of the calculation chain are not interdependent and can be calculated at the same time. You can configure Excel to use multiple threads on a single processor computer, or a single thread on a multi-processor or multi-core computer.</span></span> 
  
## <a name="asynchronous-user-defined-functions-udfs"></a><span data-ttu-id="caa1f-152">Asynchrone benutzerdefinierte Funktionen (User-Defined Functions, UDFs)</span><span class="sxs-lookup"><span data-stu-id="caa1f-152">Asynchronous User Defined Functions (UDFs)</span></span>

<span data-ttu-id="caa1f-p109">Wenn eine Berechnung eine asynchrone UDF erkennt, wird der Status der aktuellen Formel gespeichert, die UDF-Datei gestartet und die Auswertung der restlichen Zellen fortgesetzt. Nach Abschluss der Zellenauswertung wartet Excel auf den Abschluss der asynchronen Funktionen, sofern noch asynchrone Funktionen ausgef�hrt werden. Nachdem die einzelnen asynchronen Funktionen Ergebnisse gemeldet haben, beendet Excel die Formel und f�hrt dann einen neuen Berechnungslauf durch, um Zellen neu zu berechnen, die die Zelle mit dem Verweis auf die asynchrone Funktion verwenden.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p109">When a calculation encounters an asynchronous UDF, it saves the state of the current formula, starts the UDF and continues evaluating the rest of the cells. When the calculation finishes evaluating the cells Excel waits for the asynchronous functions to complete if there are still asynchronous functions running. As each asynchronous function reports results, Excel finishes the formula, and then runs a new calculation pass to re-compute cells that use the cell with the reference to the asynchronous function.</span></span>
  
## <a name="volatile-and-non-volatile-functions"></a><span data-ttu-id="caa1f-156">Ver�nderliche und nicht ver�nderliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="caa1f-156">Volatile and Non-Volatile Functions</span></span>

<span data-ttu-id="caa1f-p110">Excel unterst�tzt das Konzept einer ver�nderlichen Funktion; dies ist eine Funktion, deren Wert sich auch dann von einem Moment zum n�chsten �ndern kann, wenn keines ihrer Argumente (sofern vorhanden) ge�ndert wurde. Excel wertet Zellen mit ver�nderliche Funktionen und alle untergeordneten Zellen bei jeder Neuberechnung neu aus. Aus diesem Grund kann die Verwendung einer gro�en Anzahl von ver�nderlichen Funktionen die Neuberechnung verlangsamen. Verwenden Sie diese Funktionen m�glichst selten.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p110">Excel supports the concept of a volatile function, that is, one whose value cannot be assumed to be the same from one moment to the next even if none of its arguments (if it takes any) has changed. Excel reevaluates cells that contain volatile functions, together with all dependents, every time that it recalculates. For this reason, too much reliance on volatile functions can make recalculation times slow. Use them sparingly.</span></span>
  
<span data-ttu-id="caa1f-161">Die folgenden Excel-Funktionen sind ver�nderlich:</span><span class="sxs-lookup"><span data-stu-id="caa1f-161">The following Excel functions are volatile:</span></span>
  
- <span data-ttu-id="caa1f-162">**NOW**</span><span class="sxs-lookup"><span data-stu-id="caa1f-162">**NOW**</span></span>
    
- <span data-ttu-id="caa1f-163">**TODAY**</span><span class="sxs-lookup"><span data-stu-id="caa1f-163">**TODAY**</span></span>
    
- <span data-ttu-id="caa1f-164">**RANDBETWEEN**</span><span class="sxs-lookup"><span data-stu-id="caa1f-164">**RANDBETWEEN**</span></span>
    
- <span data-ttu-id="caa1f-165">**OFFSET**</span><span class="sxs-lookup"><span data-stu-id="caa1f-165">**OFFSET**</span></span>
    
- <span data-ttu-id="caa1f-166">**INDIRECT**</span><span class="sxs-lookup"><span data-stu-id="caa1f-166">**INDIRECT**</span></span>
    
- <span data-ttu-id="caa1f-167">**INFO** (abh�ngig von den Argumenten)</span><span class="sxs-lookup"><span data-stu-id="caa1f-167">**INFO** (depending on its arguments)</span></span> 
    
- <span data-ttu-id="caa1f-168">**CELL** (abh�ngig von den Argumenten)</span><span class="sxs-lookup"><span data-stu-id="caa1f-168">**CELL** (depending on its arguments)</span></span> 
    
- <span data-ttu-id="caa1f-169">**SUMMEWENN** (in Abhängigkeit vom Argumente)</span><span class="sxs-lookup"><span data-stu-id="caa1f-169">**SUMIF** (depending on its arguments)</span></span> 
    
<span data-ttu-id="caa1f-p111">Sowohl VBA als auch die C-API bieten M�glichkeiten, Excel dar�ber zu informieren, dass eine benutzerdefinierte Funktion (UDF) als ver�nderlich behandelt werden soll. Bei Verwendung von VBA wird die UDF wie folgt als ver�nderlich deklariert.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p111">Both the VBA and C API support ways to inform Excel that a user-defined function (UDF) should be handled as volatile. By using VBA, the UDF is declared as volatile as follows.</span></span>
  
```vb
Function MyUDF(MakeMeVolatile As Boolean) As Double
   ' Good practice to call this on the first line.
   Application.Volatile (MakeMeVolatile)
   MyUDF = Now
End Function

```

<span data-ttu-id="caa1f-p112">Standardm��ig geht Excel davon aus, dass VBA-UDFs nicht ver�nderlich sind. Excel erf�hrt erst beim ersten Aufruf einer UDF, dass diese ver�nderlich ist. Eine ver�nderliche UDF kann wie in diesem Beispiel gezeigt wieder als nicht ver�nderlich festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p112">By default, Excel assumes that VBA UDFs are not volatile. Excel only learns that a UDF is volatile when it first calls it. A volatile UDF can be changed back to non-volatile as in this example.</span></span>
  
<span data-ttu-id="caa1f-p113">Mit der C-API k�nnen Sie eine XLL-Funktion schon vor dem ersten Aufruf als ver�nderlich registrieren. Au�erdem k�nnen Sie den ver�nderlichen Status einer Arbeitsblattfunktion damit ein- und ausschalten.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p113">Using the C API, you can register an XLL function as volatile before its first call. It also enables you to switch on and off the volatile status of a worksheet function.</span></span>
  
<span data-ttu-id="caa1f-p114">Standardm��ig werden XLL-UDFs, die Bereichsargumente akzeptieren und als Makrovorlagenentsprechungen deklariert sind, von Excel als unver�nderlich behandelt. Sie k�nnen diesen Standardstatus beim ersten Aufruf der UDF mit der **xlfVolatile**-Funktion deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p114">By default, Excel handles XLL UDFs that take range arguments and that are declared as macro-sheet equivalents as volatile. You can turn this default state off using the **xlfVolatile** function when the UDF is first called.</span></span> 
  
## <a name="calculation-modes-commands-selective-recalculation-and-data-tables"></a><span data-ttu-id="caa1f-179">Berechnungsmodi, Befehle, selektive Neuberechnung und Datentabellen</span><span class="sxs-lookup"><span data-stu-id="caa1f-179">Calculation Modes, Commands, Selective Recalculation, and Data Tables</span></span>

<span data-ttu-id="caa1f-180">Excel verf�gt �ber drei Berechnungsmodi:</span><span class="sxs-lookup"><span data-stu-id="caa1f-180">Excel has three calculation modes:</span></span>
  
- <span data-ttu-id="caa1f-181">Automatisch</span><span class="sxs-lookup"><span data-stu-id="caa1f-181">Automatic</span></span>
    
- <span data-ttu-id="caa1f-182">Automatisch au�er bei Datentabellen</span><span class="sxs-lookup"><span data-stu-id="caa1f-182">Automatic Except Tables</span></span>
    
- <span data-ttu-id="caa1f-183">Manuell</span><span class="sxs-lookup"><span data-stu-id="caa1f-183">Manual</span></span>
    
<span data-ttu-id="caa1f-p115">Im automatischen Berechnungsmodus erfolgt die Neuberechnung nach jeder Dateneingabe und nach bestimmten Ereignissen, wie z.�B. den im vorherigen Abschnitt genannten Beispielen. F�r sehr gro�e Arbeitsmappen ist die Neuberechnungszeit m�glicherweise so lang, dass Benutzer Neuberechnungen auf absolut erforderliche F�lle beschr�nken m�ssen. Hierzu unterst�tzt Excel den manuellen Modus. Der Benutzer kann den Modus �ber das Excel-Men�system oder programmgesteuert mithilfe von VBA, COM oder der C-API ausw�hlen.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p115">When calculation is set to automatic, recalculation occurs after every data input and after certain events such as the examples given in the previous section. For very large workbooks, recalculation time might be so long that users must limit when this happens, that is, only recalculating when they need to. To enable this, Excel supports the manual mode. The user can select the mode through the Excel menu system, or programmatically using VBA, COM, or the C API.</span></span>
  
<span data-ttu-id="caa1f-p116">Datentabellen sind spezielle Strukturen in einem Arbeitsblatt. Der Benutzer richtet zuerst die Berechnung des Ergebnisses auf einem Arbeitsblatt ein. Diese h�ngt von einer oder zwei ver�nderbaren Schl�sseleingaben und anderen Parametern ab. Der Benutzer kann dann eine Tabelle mit Ergebnissen f�r einen Satz von Werten f�r eine oder beide Schl�sseleingaben erstellen. Die Tabelle wird mit dem **Assistenten f�r Datentabellen** erstellt. Nachdem die Tabelle eingerichtet wurde, f�gt Excel die Eingaben einzeln nacheinander in die Berechnung ein und kopiert den resultierenden Wert in die Tabelle. Da eine oder zwei Eingaben verwendet werden k�nnen, k�nnen Datentabellen ein- oder zweidimensional sein.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p116">Data tables are special structures in a worksheet. First, the user sets up the calculation of a result on a worksheet. This depends on one or two key changeable inputs and other parameters. The user can then create a table of results for a set of values for one or both of the key inputs. The table is created by using the **Data Table Wizard**. After the table is set up, Excel plugs the inputs one-by-one into the calculation and copies the resulting value into the table. As one or two inputs can be used, data tables can be one- or two-dimensional.</span></span> 
  
<span data-ttu-id="caa1f-195">Die Neuberechnung von Datentabellen wird etwas anders gehandhabt:</span><span class="sxs-lookup"><span data-stu-id="caa1f-195">Recalculation of data tables is handled slightly differently:</span></span>
  
- <span data-ttu-id="caa1f-196">Die Neuberechnung erfolgt asynchron zur normalen Neuberechnung der Arbeitsmappe, sodass die Neuberechnung gro�er Tabellen l�nger dauern kann der Vorgang f�r den Rest der Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="caa1f-196">Recalculation is handled asynchronously to regular workbook recalculation so that large tables might take longer to recalculate than the rest of the workbook.</span></span>
    
- <span data-ttu-id="caa1f-p117">Zirkelbez�ge sind zul�ssig. Wenn die zur Ermittlung des Ergebnisses verwendete Berechnung von einem oder mehreren Werten aus der Datentabelle abh�ngt, gibt Excel keinen Fehler f�r den Zirkelbezug zur�ck.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p117">Circular references are tolerated. If the calculation that is used to get the result depends on one or more values from the data table, Excel does not return an error for the circular dependency.</span></span> 
    
<span data-ttu-id="caa1f-p118">Da Excel die Neuberechnung von Datentabellen anders handhabt und die Berechnung gro�er Tabellen, die komplexe oder langwierige Berechnungen erfordern, sehr lange dauern kann, haben Sie in Excel die M�glichkeit, die automatische Berechnung von Datentabellen zu deaktivieren. Legen Sie hierzu den Berechnungsmodus auf "Automatisch au�er bei Datentabellen" fest. Wenn dieser Berechnungsmodus aktiv ist, dr�ckt der Benutzer F9 oder f�hrt einen entsprechenden Programmiervorgang aus, um die Datentabellen neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p118">Given the different way that Excel handles recalculation of data tables, and the fact that large tables that depend on complex or lengthy calculations can take a long time to calculate, Excel lets you disable the automatic calculation of data tables. To do this, set the calculation mode to Automatic except Data Tables. When calculation is in this mode, the user recalculates the data tables by pressing F9 or some equivalent programmatic operation.</span></span>
  
<span data-ttu-id="caa1f-p119">Excel stellt Methoden zur Verf�gung, mit denen Sie den Neuberechnungsmodus �ndern und die Neuberechnung steuern k�nnen. Diese Methoden wurden von Version zu Version verbessert, um eine pr�zisere Steuerung zu erm�glichen. Die betreffenden Funktionen der C-API entsprechen denen in Excel, Version 5, und bieten daher nicht das Ma� an Steuerung, von dem Sie bei Verwendung von VBA in neueren Versionen profitieren.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p119">Excel exposes methods through which you can alter the recalculation mode and control recalculation. These methods have been improved from version to version to allow for finer control. The capabilities of the C API in this regard reflect those that were available in Excel version 5, and so do not give you the same control that you have using VBA in more recent versions.</span></span> 
  
<span data-ttu-id="caa1f-205">Diese Methoden werden am h�ufigsten verwendet, wenn sich Excel im manuellen Berechnungsmodus befindet, und erlauben die selektive Berechnung von Arbeitsmappen, Arbeitsbl�ttern und Bereichen, die vollst�ndige Neuberechnung aller ge�ffneten Arbeitsmappen und sogar die vollst�ndige Neuerstellung der Abh�ngigkeitsstruktur und der Berechnungskette.</span><span class="sxs-lookup"><span data-stu-id="caa1f-205">Most frequently used when Excel is in manual calculation mode, these methods allow selective calculation of workbooks, worksheets, and ranges, complete recalculation of all open workbooks, and even complete rebuild of the dependency tree and calculation chain.</span></span>
  
### <a name="range-calculation"></a><span data-ttu-id="caa1f-206">Bereichsberechnung</span><span class="sxs-lookup"><span data-stu-id="caa1f-206">Range Calculation</span></span>

<span data-ttu-id="caa1f-207">Tastenkombination: keine</span><span class="sxs-lookup"><span data-stu-id="caa1f-207">Keystroke: None</span></span>
  
<span data-ttu-id="caa1f-208">VBA: **Range.Calculate** (eingef�hrt in Excel 2000, ge�ndert in Excel 2007) und **Range.CalculateRowMajorOrder** (eingef�hrt in Excel 2007)</span><span class="sxs-lookup"><span data-stu-id="caa1f-208">VBA: **Range.Calculate** (introduced in Excel 2000, changed in Excel 2007) and **Range.CalculateRowMajorOrder** (introduced in Excel 2007)</span></span> 
  
<span data-ttu-id="caa1f-209">C-API: nicht unterst�tzt</span><span class="sxs-lookup"><span data-stu-id="caa1f-209">C API: Not supported</span></span>
  
- <span data-ttu-id="caa1f-210">**Manueller Modus**</span><span class="sxs-lookup"><span data-stu-id="caa1f-210">**Manual mode**</span></span>
    
    <span data-ttu-id="caa1f-p120">Berechnet nur die Zellen im angegebenen Bereich neu, unabh�ngig davon, ob sie ge�ndert wurden oder nicht. Das Verhalten der **Range.Calculate**-Methode wurde in Excel 2007 ge�ndert; das alte Verhalten wird jedoch noch von der **Range.CalculateRowMajorOrder** -Methode unterst�tzt.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p120">Recalculates just the cells in the given range regardless of whether they are dirty or not. Behavior of the **Range.Calculate** method changed in Excel 2007; however, the old behavior is still supported by the **Range.CalculateRowMajorOrder** method.</span></span> 
    
- <span data-ttu-id="caa1f-213">**Modi "Automatisch" und "Automatisch au�er bei Datentabellen"**</span><span class="sxs-lookup"><span data-stu-id="caa1f-213">**Automatic or Automatic Except Tables modes**</span></span>
    
    <span data-ttu-id="caa1f-214">Berechnet die Arbeitsmappe neu, erzwingt jedoch keine Neuberechnung des Bereichs oder einer Zelle im Bereich.</span><span class="sxs-lookup"><span data-stu-id="caa1f-214">Recalculates the workbook but does not force recalculation of the range or any cells in the range.</span></span>
    
### <a name="active-worksheet-calculation"></a><span data-ttu-id="caa1f-215">Berechnung des aktiven Arbeitsblatts</span><span class="sxs-lookup"><span data-stu-id="caa1f-215">Active Worksheet Calculation</span></span>

<span data-ttu-id="caa1f-216">Tastenkombination: UMSCHALT + F9</span><span class="sxs-lookup"><span data-stu-id="caa1f-216">Keystroke: SHIFT+F9</span></span>
  
<span data-ttu-id="caa1f-217">VBA: **ActiveSheet.Calculate**</span><span class="sxs-lookup"><span data-stu-id="caa1f-217">VBA: **ActiveSheet.Calculate**</span></span>
  
<span data-ttu-id="caa1f-218">C-API: **xlcCalculateDocument**</span><span class="sxs-lookup"><span data-stu-id="caa1f-218">C API: **xlcCalculateDocument**</span></span>
  
- <span data-ttu-id="caa1f-219">**Alle Modi**</span><span class="sxs-lookup"><span data-stu-id="caa1f-219">**All modes**</span></span>
    
    <span data-ttu-id="caa1f-220">Berechnet nur die Zellen neu, die im aktiven Arbeitsblatt als zu berechnen markiert sind.</span><span class="sxs-lookup"><span data-stu-id="caa1f-220">Recalculates the cells marked for calculation in the active worksheet only.</span></span>
    
### <a name="specified-worksheet-calculation"></a><span data-ttu-id="caa1f-221">Berechnung des angegebenen Arbeitsblatts</span><span class="sxs-lookup"><span data-stu-id="caa1f-221">Specified Worksheet Calculation</span></span>

<span data-ttu-id="caa1f-222">Tastenkombination: keine</span><span class="sxs-lookup"><span data-stu-id="caa1f-222">Keystroke: None</span></span>
  
<span data-ttu-id="caa1f-223">VBA: **Worksheets(** Reference **).Calculate**</span><span class="sxs-lookup"><span data-stu-id="caa1f-223">VBA: **Worksheets(** reference **).Calculate**</span></span>
  
<span data-ttu-id="caa1f-224">C-API: nicht unterst�tzt</span><span class="sxs-lookup"><span data-stu-id="caa1f-224">C API: Not supported</span></span>
  
- <span data-ttu-id="caa1f-225">**Alle Modi**</span><span class="sxs-lookup"><span data-stu-id="caa1f-225">**All modes**</span></span>
    
    <span data-ttu-id="caa1f-p121">Berechnet nur die ge�nderten Zellen und ihre abh�ngigen Zellen innerhalb des angegebenen Arbeitsblatts neu. "Reference" ist der Name des Arbeitsblatts als Zeichenfolge oder die Indexnummer in der entsprechenden Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p121">Recalculates the dirty cells and their dependents within the specified worksheet only. Reference is the name of the worksheet as a string or the index number in the relevant workbook.</span></span>
    
    <span data-ttu-id="caa1f-p122">In Excel 2000 und sp�teren Versionen steht eine **Boolean**-Arbeitsblatteigenschaft zur Verf�gung, die **EnableCalculation**-Eigenschaft. Durch Festlegen dieser Eigenschaft auf **True** von **False** werden alle Zellen im angegebenen Arbeitsblatt als ge�ndert definiert. In automatischen Modi l�st dies au�erdem eine Neuberechnung der gesamten Arbeitsmappe aus.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p122">Excel 2000 and later versions expose a **Boolean** worksheet property, the **EnableCalculation** property. Setting this to **True** from **False** dirties all cells in the specified worksheet. In automatic modes, this also triggers a recalculation of the whole workbook.</span></span> 
    
    <span data-ttu-id="caa1f-231">Im manuellen Modus bewirkt der folgende Code, dass nur das aktive Blatt neu berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="caa1f-231">In manual mode, the following code causes recalculation of the active sheet only.</span></span>
    
  ```vb
  With ActiveSheet
    .EnableCalculation = False
    .EnableCalculation = True
    .Calculate
  End With
  
  ```

### <a name="workbook-tree-rebuild-and-forced-recalculation"></a><span data-ttu-id="caa1f-232">Neuerstellung der Arbeitsmappenstruktur und erzwungene Neuberechnung</span><span class="sxs-lookup"><span data-stu-id="caa1f-232">Workbook Tree Rebuild and Forced Recalculation</span></span>

<span data-ttu-id="caa1f-233">Tastenkombination: STRG + ALT + UMSCHALT + F9 (eingef�hrt in Excel 2002)</span><span class="sxs-lookup"><span data-stu-id="caa1f-233">Keystroke: CTRL+ALT+SHIFT+F9 (introduced in Excel 2002)</span></span>
  
<span data-ttu-id="caa1f-234">VBA: **Workbooks(** Reference **).ForceFullCalculation** (eingef�hrt in Excel 2007)</span><span class="sxs-lookup"><span data-stu-id="caa1f-234">VBA: **Workbooks(** reference **).ForceFullCalculation** (introduced in Excel 2007)</span></span> 
  
<span data-ttu-id="caa1f-235">C-API: nicht unterst�tzt</span><span class="sxs-lookup"><span data-stu-id="caa1f-235">C API: Not supported</span></span>
  
- <span data-ttu-id="caa1f-236">**Alle Modi**</span><span class="sxs-lookup"><span data-stu-id="caa1f-236">**All modes**</span></span>
    
    <span data-ttu-id="caa1f-237">Bewirkt, dass Excel die Abh�ngigkeitsstruktur und die Berechnungskette f�r eine bestimmte Arbeitsmappe neu berechnet, und erzwingt eine Neuberechnung aller Zellen, die Formeln enthalten.</span><span class="sxs-lookup"><span data-stu-id="caa1f-237">Causes Excel to rebuild the dependency tree and the calculation chain for a given workbook and forces a recalculation of all cells that contain formulas.</span></span>
    
### <a name="all-open-workbooks"></a><span data-ttu-id="caa1f-238">Alle ge�ffneten Arbeitsmappen</span><span class="sxs-lookup"><span data-stu-id="caa1f-238">All Open Workbooks</span></span>

<span data-ttu-id="caa1f-239">Tastenkombination: F9</span><span class="sxs-lookup"><span data-stu-id="caa1f-239">Keystroke: F9</span></span>
  
<span data-ttu-id="caa1f-240">VBA: **Application.Calculate**</span><span class="sxs-lookup"><span data-stu-id="caa1f-240">VBA: **Application.Calculate**</span></span>
  
<span data-ttu-id="caa1f-241">C-API: **xlcCalculateNow**</span><span class="sxs-lookup"><span data-stu-id="caa1f-241">C API: **xlcCalculateNow**</span></span>
  
- <span data-ttu-id="caa1f-242">**Alle Modi**</span><span class="sxs-lookup"><span data-stu-id="caa1f-242">**All modes**</span></span>
    
    <span data-ttu-id="caa1f-p123">Berechnet alle Zellen neu, die Excel als ge�ndert markiert hat, d.�h. abh�ngige Elemente von ver�nderlichen oder ge�nderten Daten sowie programmgesteuert als ge�ndert markierte Zellen. Im Berechnungsmodus "Automatisch au�er bei Datentabellen" werden die Tabellen berechnet, die aktualisiert werden m�ssen, sowie alle ver�nderlichen Funktionen und ihre abh�ngigen Elemente.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p123">Recalculates all cells that Excel has marked as dirty, that is, dependents of volatile or changed data, and cells programmatically marked as dirty. If the calculation mode is Automatic Except Tables, this calculates those tables that require updating and also all volatile functions and their dependents.</span></span>
    
### <a name="all-open-workbooks-tree-rebuild-and-forced-calculation"></a><span data-ttu-id="caa1f-245">Neuerstellung der Struktur und erzwungene Berechnung f�r alle ge�ffneten Arbeitsmappen</span><span class="sxs-lookup"><span data-stu-id="caa1f-245">All Open Workbooks Tree Rebuild and Forced Calculation</span></span>

<span data-ttu-id="caa1f-246">Tastenkombination: STRG + ALT + F9.</span><span class="sxs-lookup"><span data-stu-id="caa1f-246">Keystroke: CTRL+ALT+F9</span></span>
  
<span data-ttu-id="caa1f-247">VBA: **Application.CalculateFull**</span><span class="sxs-lookup"><span data-stu-id="caa1f-247">VBA: **Application.CalculateFull**</span></span>
  
<span data-ttu-id="caa1f-248">C-API: nicht unterst�tzt</span><span class="sxs-lookup"><span data-stu-id="caa1f-248">C API: Not supported</span></span>
  
- <span data-ttu-id="caa1f-249">**Alle Modi**</span><span class="sxs-lookup"><span data-stu-id="caa1f-249">**All modes**</span></span>
    
    <span data-ttu-id="caa1f-p124">Berechnet alle Zellen in allen ge�ffneten Arbeitsmappen neu. Im Berechnungsmodus "Automatisch au�er bei Datentabellen" wird die Neuberechnung der Tabellen erzwungen.</span><span class="sxs-lookup"><span data-stu-id="caa1f-p124">Recalculates all cells in all open workbooks. If the calculation mode is Automatic Except Tables, it forces the tables to be recalculated.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="caa1f-252">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caa1f-252">See also</span></span>



[<span data-ttu-id="caa1f-253">Multithread-Neuberechnung in Excel</span><span class="sxs-lookup"><span data-stu-id="caa1f-253">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="caa1f-254">Datentypen von Excel verwendet</span><span class="sxs-lookup"><span data-stu-id="caa1f-254">Data Types Used by Excel</span></span>](data-types-used-by-excel.md)
  
[<span data-ttu-id="caa1f-255">Speicherverwaltung in Excel</span><span class="sxs-lookup"><span data-stu-id="caa1f-255">Memory Management in Excel</span></span>](memory-management-in-excel.md)
  
[<span data-ttu-id="caa1f-256">Excel-Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="caa1f-256">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
