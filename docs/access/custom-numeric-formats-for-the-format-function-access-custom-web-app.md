---
title: Benutzerdefinierte numerische Formate für die Formatfunktion (benutzerdefinierte Access-Web-App)
manager: kelbow
ms.date: 08/18/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 97efe972-d873-47d7-be81-8ae3461870c4
description: Hier erfahren Sie, wie Sie die Darstellung einer Zahl durch das Erstellen eines benutzerdefinierten Zahlenformats steuern.
ms.openlocfilehash: fac128ce13edf89105fbee7319533e1a3f346d05
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790224"
---
# <a name="custom-numeric-formats-for-the-format-function-access-custom-web-app"></a><span data-ttu-id="d7908-103">Benutzerdefinierte numerische Formate für die Formatfunktion (benutzerdefinierte Access-Web-App)</span><span class="sxs-lookup"><span data-stu-id="d7908-103">Custom numeric formats for the Format function (Access custom web app)</span></span>

<span data-ttu-id="d7908-104">Hier erfahren Sie, wie Sie die Darstellung einer Zahl durch das Erstellen eines benutzerdefinierten Zahlenformats steuern.</span><span class="sxs-lookup"><span data-stu-id="d7908-104">Learn how to control how a number is displayed by creating a user-defined number format.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d7908-p101">[!WICHTIG] Das Erstellen und Verwenden von Access-Web-Apps in SharePoint wird von Microsoft nicht mehr empfohlen. Alternativ sollten Sie die Verwendung von [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) für das Erstellen von Business Solutions ohne Code für das Web und für mobile Geräte in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="d7908-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 

<span data-ttu-id="d7908-p102">Sie können die Darstellung einer Zahl ändern, indem Sie ein benutzerdefiniertes Zahlenformat erstellen. Ein benutzerdefiniertes Zahlenformat kann über ein bis drei Teile, die durch ein Semikolon (;) getrennt sind, verfügen. Wenn das Formatargument der [Format-Funktion (Access benutzerdefinierte Web app)](format-function-access-custom-web-app.md)-Funktion eines der vordefinierten numerischen Formate enthält, ist nur ein Teil zulässig.</span><span class="sxs-lookup"><span data-stu-id="d7908-p102">You can change the way a number is displayed by creating a user-defined number format. A user-defined number format can have from one to three sections separated by a semicolon (;). If the Style argument of the [Format Function (Access custom web app)](format-function-access-custom-web-app.md) function contains one of the predefined numeric formats, only one section is allowed.</span></span> 
  
## <a name="format-specifications"></a><span data-ttu-id="d7908-110">Spezifikationen</span><span class="sxs-lookup"><span data-stu-id="d7908-110">Format specifications</span></span>
<span data-ttu-id="d7908-111"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="d7908-111"></span></span>

<span data-ttu-id="d7908-112">In der folgenden Tabelle sind die Zeichen aufgeführt, die Sie zum Erstellen benutzerdefinierter Zahlenformate verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d7908-112">The following table lists characters you can use to create user-defined number formats.</span></span>
  
|<span data-ttu-id="d7908-113">**Formatspezifikationen**</span><span class="sxs-lookup"><span data-stu-id="d7908-113">**Format specification**</span></span>|<span data-ttu-id="d7908-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d7908-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d7908-115">Keine</span><span class="sxs-lookup"><span data-stu-id="d7908-115">None</span></span>  <br/> |<span data-ttu-id="d7908-116">Zeigt die Zahl ohne Formatierung an.</span><span class="sxs-lookup"><span data-stu-id="d7908-116">Displays the number without formatting.</span></span>  <br/> |
|<span data-ttu-id="d7908-117">**0** (Null)</span><span class="sxs-lookup"><span data-stu-id="d7908-117">**0** (zero character)</span></span>  <br/> |<span data-ttu-id="d7908-p103">Ziffernplatzhalter. Zeigt eine Ziffer oder eine Null an. Wenn im Ausdruck in der Formatzeichenfolge an der Position der Null eine Ziffer steht, wird die Ziffer angezeigt. Andernfalls wird an dieser Position eine Null angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p103">Digit placeholder. Displays a digit or a zero. If the expression has a digit in the position where the zero appears in the format string, displays the digit; otherwise, displays a zero in that position.</span></span>  <br/> <span data-ttu-id="d7908-p104">Wenn die Zahl im Formatausdruck weniger Ziffern als Nullen aufweist (auf einer von beiden Seiten des Dezimaltrennzeichens) werden voran- oder nachgestellte Nullen angezeigt. Weist die Zahl rechts neben dem Dezimaltrennzeichen mehr Ziffern als Nullen auf als rechts neben dem Dezimaltrennzeichen im Formatausdruck, wird die Zahl entsprechend der Anzahl an vorhandenen Nullen gerundet. Weist die Zahl links neben dem Dezimaltrennzeichen mehr Ziffern als Nullen auf als links neben dem Dezimaltrennzeichen im Formatausdruck, werden die zusätzlichen Ziffern unverändert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p104">If the number has fewer digits than there are zeros (on either side of the decimal) in the format expression, displays leading or trailing zeros. If the number has more digits to the right side of the decimal separator than there are zeros to the right side of the decimal separator in the format expression, rounds the number to as many decimal places as there are zeros. If the number has more digits to the left of the decimal separator than there are zeros to the left of the decimal separator in the format expression, displays the additional digits without modification.</span></span>  <br/> |
|#  <br/> |<span data-ttu-id="d7908-p105">Ziffernplatzhalter. Zeigt eine Ziffer oder nichts an. Wenn im Ausdruck in der Formatzeichenfolge an der Position von „#" eine Ziffer steht, wird die Ziffer angezeigt. Andernfalls wird an dieser Position nichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p105">Digit placeholder. Displays a digit or nothing. If the expression has a digit in the position where the # character appears in the format string, displays the digit; otherwise, displays nothing in that position.</span></span>  <br/> <span data-ttu-id="d7908-127">Dieses Symbol funktioniert so wie der Ziffernplatzhalter „0", nur dass keine voran- und nachgestellte Nullen angezeigt werden, wenn die Zahl auf einer von beiden Seiten des Dezimaltrennzeichens im Formatausdruck die gleiche oder eine geringere Anzahl an Ziffern als „#"-Zeichen aufweist.</span><span class="sxs-lookup"><span data-stu-id="d7908-127">This symbol works exactly like the 0 digit placeholder, except that leading and trailing zeros aren't displayed if the number has fewer digits than there are # characters on either side of the decimal separator in the format expression.</span></span>  <br/> |
|<span data-ttu-id="d7908-p106">. (Punkt)</span><span class="sxs-lookup"><span data-stu-id="d7908-p106">. (dot character)</span></span>  <br/> |<span data-ttu-id="d7908-p107">Dezimalplatzhalter. Der Dezimalplatzhalter bestimmt, wie viele Ziffern rechts und links neben dem Dezimaltrennzeichen angezeigt werden. Sind im Formatausdruck nur #-Zeichen neben diesem Symbol enthalten, beginnen Zahlen unter 1 mit einem Dezimaltrennzeichen. Um eine vorangestellte Null mit Bruchzahlen anzuzeigen, wird die Null als erster Ziffernplatzhalter links neben dem Dezimaltrennzeichen verwendet. In manchen Gebietsschemas wird ein Komma als Dezimaltrennzeichen verwendet. Das tatsächliche in der formatierten Ausgabe als Dezimaltrennzeichen verwendete Zeichen hängt von dem vom System erkannten Zahlenformat ab. Daher sollten Sie auch dann den Punkt als Dezimaltrennzeichen in den Formaten verwenden, wenn Sie sich in einem Gebietsschema befinden, in dem ein Komma als Dezimaltrennzeichen verwendet wird. Die formatierte Zeichenfolge wird in dem für das Gebietsschema korrekten Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p107">Decimal placeholder. The decimal placeholder determines how many digits are displayed to the left and right of the decimal separator. If the format expression contains only # characters to the left of this symbol; numbers smaller than 1 begin with a decimal separator. To display a leading zero displayed with fractional numbers, use zero as the first digit placeholder to the left of the decimal separator. In some locales, a comma is used as the decimal separator. The actual character that is used as a decimal placeholder in the formatted output depends on the number format recognized by the system. Thus, you should use the period as the decimal placeholder in your formats even if you are in a locale that uses a comma as a decimal placeholder. The formatted string will appear in the format correct for the locale.</span></span>  <br/> |
|%  <br/> |<span data-ttu-id="d7908-p108">Prozentplatzhalter. Der Ausdruck wird mit 100 multipliziert. Das Prozentzeichen (%) wird an der Position eingefügt, an der es in der Formatzeichenfolge steht.</span><span class="sxs-lookup"><span data-stu-id="d7908-p108">Percent placeholder. Multiplies the expression by 100. The percent character (%) is inserted in the position where it appears in the format string.</span></span>  <br/> |
|<span data-ttu-id="d7908-141">, (Komma)</span><span class="sxs-lookup"><span data-stu-id="d7908-141">, (comma character)</span></span>  <br/> |<span data-ttu-id="d7908-p109">Tausendertrennzeichen. Das Tausendertrennzeichen trennt die Tausend von Hundert in einer Zahl, die vier oder mehr Stellen links neben dem Dezimaltrennzeichen aufweist. Der standardmäßige Gebrauch des Tausendertrennzeichens ist gegeben, wenn das Format ein Tausendertrennzeichen aufweist, das von Ziffernplatzhaltern umschlossen ist (0 oder #).</span><span class="sxs-lookup"><span data-stu-id="d7908-p109">Thousand separator. The thousand separator separates thousands from hundreds in a number that has four or more places to the left of the decimal separator. Standard use of the thousand separator is specified if the format contains a thousand separator enclosed in digit placeholders (0 or #).</span></span>  <br/> <span data-ttu-id="d7908-p110">Ein Tausendertrennzeichen direkt links neben dem Dezimaltrennzeichen (falls eine Dezimalzahl angegeben ist) oder als Zeichen ganz rechts in der Zeichenfolge bedeutet, dass die Zahl durch 1000 dividiert und bei Bedarf entsprechend gerundet wird. Zahlen, die kleiner als 1000, jedoch größer oder gleich 500 sind, werden als 1 angezeigt, und Zahlen, die kleiner als 500 sind, werden als 0 angezeigt. Zwei aufeinanderfolgende Tausendertrennzeichen an dieser Stelle skalieren mit einem Faktor von 1 Million sowie einem weiteren Faktor von 1000 für jedes weitere Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="d7908-p110">A thousand separator immediately to the left of the decimal separator (whether a decimal is specified) or as the rightmost character in the string means "scale the number by dividing it by 1,000, rounding as needed." Numbers smaller than 1,000 but greater or equal to 500 are displayed as 1, and numbers smaller than 500 are displayed as 0. Two adjacent thousand separators in this position scale by a factor of 1 million, and an additional factor of 1,000 for each additional separator.</span></span>  <br/> <span data-ttu-id="d7908-p111">Mehrere Trennzeichen an anderer Position als direkt links neben dem Dezimaltrennzeichen oder ganz rechts in der Zeichenfolge werden so behandelt, als ob sie nur die Verwendung des Tausendertrennzeichens angeben würden. In einigen Gebietsschemas wird ein Punkt als Tausendertrennzeichen verwendet. Das tatsächliche in der formatierten Ausgabe als Tausendertrennzeichen verwendete Zeichen hängt von dem von Ihrem System erkannten Zahlenformat ab. Daher sollten auch dann das Komma als Tausendertrennzeichen in den Formaten verwenden, wenn Sie sich in einem Gebietsschema befinden, in dem ein Punkt als Tausendertrennzeichen verwendet wird. Die formatierte Zeichenfolge wird in dem für das Gebietsschema korrekten Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p111">Multiple separators in any position other than immediately to the left of the decimal separator or the rightmost position in the string are treated only as specifying the use of a thousand separator. In some locales, a period is used as a thousand separator. The actual character that is used as the thousand separator in the formatted output depends on the Number Format recognized by the system. Thus, you should use the comma as the thousand separator in your formats even if you are in a locale that uses a period as a thousand separator. The formatted string will appear in the format correct for the locale.</span></span>  <br/> <span data-ttu-id="d7908-153">Sehen Sie sich zum Beispiel die folgenden drei Formatierungszeichenfolgen an:</span><span class="sxs-lookup"><span data-stu-id="d7908-153">For example, consider the three following format strings:</span></span>  <br/> <span data-ttu-id="d7908-154">„#,0." verwendet das Tausendertrennzeichen, um die Zahl 100 Millionen als Zeichenfolge „100,000,000" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d7908-154">"#,0.", which uses the thousands separator to format the number 100 million as the string "100,000,000".</span></span>  <br/> <span data-ttu-id="d7908-155">„#0,." verwendet die Skalierung mit einem Faktor von Eintausend, um die Zahl 100 Millionen als Zeichenfolge „100000" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d7908-155">"#0,.", which uses scaling by a factor of one thousand to format the number 100 million as the string "100000".</span></span>  <br/> <span data-ttu-id="d7908-156">„#,0,." verwendet das Tausendertrennzeichen und die Skalierung mit Eintausend, um die Zahl 100 Millionen als Zeichenfolge „100,000" zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="d7908-156">"#,0,.", which uses the thousands separator and scaling by one thousand to format the number 100 million as the string "100,000".</span></span>  <br/> |
|<span data-ttu-id="d7908-157">: (Doppelpunkt)</span><span class="sxs-lookup"><span data-stu-id="d7908-157">: (colon character)</span></span>  <br/> |<span data-ttu-id="d7908-p112">Zeittrennzeichen. In manchen Gebietsschemas werden andere Zeichen als Zeittrennzeichen verwendet. Das Zeittrennzeichen trennt Stunden, Minuten und Sekunden bei der Formatierung von Zeitwerten. Das tatsächliche in der formatierten Ausgabe als Zeittrennzeichen verwendete Zeichen wird durch die Systemeinstellungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p112">Time separator. In some locales, other characters may be used to represent the time separator. The time separator separates hours, minutes, and seconds when time values are formatted. The actual character that is used as the time separator in formatted output is determined by the system settings.</span></span>  <br/> |
|<span data-ttu-id="d7908-162">/ (Schrägstrich)</span><span class="sxs-lookup"><span data-stu-id="d7908-162">/ (forward slash character)</span></span>  <br/> |<span data-ttu-id="d7908-p113">Datumstrennzeichen. In manchen Gebietsschemas werden andere Zeichen als Datumstrennzeichen verwendet. Das Datumstrennzeichen trennt Tag, Monat und Jahr bei der Formatierung von Datumswerten. Das tatsächliche in der formatierten Ausgabe als Datumstrennzeichen verwendete Zeichen wird durch die Systemeinstellungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d7908-p113">Date separator. In some locales, other characters may be used to represent the date separator. The date separator separates the day, month, and year when date values are formatted. The actual character that is used as the date separator in formatted output is determined by the system settings.</span></span>  <br/> |
|<span data-ttu-id="d7908-167">**E- , E+ , e- , e+**</span><span class="sxs-lookup"><span data-stu-id="d7908-167">**E- , E+ , e- , e+**</span></span> <br/> |<span data-ttu-id="d7908-p114">Wissenschaftliches Format. Wenn der Formatausdruck mindestens einen Ziffernplatzhalter (0 oder #) rechts neben „E-", „E+", „e-" oder „e+" aufweist, wird die Zahl im wissenschaftlichen Format angezeigt und zwischen der Zahl und dem Exponenten „E" oder „e" eingefügt. Die Anzahl an Ziffernplatzhaltern auf der linken Seite bestimmt die Anzahl an Ziffern im Exponenten. „E-" oder „e-" fügt ein Minus-Zeichen neben negativen Exponenten ein. „E+" oder „e+" fügt ein Minus-Zeichen neben negativen und ein Plus-Zeichen neben positiven Exponenten ein. Zur richtigen Formatierung müssen Sie außerdem Ziffernplatzhalter rechts neben diesem Symbol einfügen.</span><span class="sxs-lookup"><span data-stu-id="d7908-p114">Scientific format. If the format expression contains at least one digit placeholder (0 or #) to the left of E-, E+, e-, or e+, the number is displayed in scientific format and E or e is inserted between the number and its exponent. The number of digit placeholders to the left determines the number of digits in the exponent. Use E- or e- to place a minus sign next to negative exponents. Use E+ or e+ to place a minus sign next to negative exponents and a plus sign next to positive exponents. You must also include digit placeholders to the right side of this symbol to achieve correct formatting.</span></span>  <br/> |
|<span data-ttu-id="d7908-174">**- + $ ( )**</span><span class="sxs-lookup"><span data-stu-id="d7908-174">**- + $ ( )**</span></span> <br/> |<span data-ttu-id="d7908-p115">Literalzeichen. Diese Zeichen werden genau so angezeigt, wie sie in der Formatierungszeichenfolge eingegeben wurden. Um ein anderes Zeichen als die aufgeführten anzuzeigen, stellen Sie ihm einen umgekehrten Schrägstrich voran (\), oder schließen Sie das Zeichen in doppelte Anführungszeichen ein (" ").</span><span class="sxs-lookup"><span data-stu-id="d7908-p115">Literal characters. These characters are displayed exactly as typed in the format string. To display a character other than one of those listed, precede it with a backslash (\) or enclose it in double quotation marks (" ").</span></span>  <br/> |
|<span data-ttu-id="d7908-178">\ (umgekehrter Schrägstrich)</span><span class="sxs-lookup"><span data-stu-id="d7908-178">\ (backward slash character)</span></span>  <br/> |<span data-ttu-id="d7908-p116">Zeigt das nächste Zeichen in der Formatzeichenfolge an. Um ein Zeichen anzuzeigen, das als Literalzeichen eine besondere Bedeutung hat, wird diesem ein umgekehrter Schrägstrich vorangestellt (\). Der umgekehrte Schrägstrich wird nicht angezeigt. Die Verwendung eines umgekehrten Schrägstrichs entspricht dem Setzen eines Zeichens in doppelte Anführungszeichen. Wenn ein umgekehrter Schrägstrich angezeigt werden soll, muss diesem ein zweiter vorangestellt werden (\\).</span><span class="sxs-lookup"><span data-stu-id="d7908-p116">Displays the next character in the format string. To display a character that has special meaning as a literal character, precede it with a backslash (\). The backslash itself isn't displayed. By using a backslash is the same as enclosing the next character in double quotation marks. To display a backslash, use two backslashes (\\).</span></span>  <br/> <span data-ttu-id="d7908-184">Zeichen, die nicht als Literalzeichen angezeigt werden können, sind die datum- und uhrzeitformatierenden Zeichen (a, c, d, h, m, n, p, q, s, t, w, y, / und :), die zahlenformatierenden Zeichen (#, 0, %, E, e, Komma und Punkt) sowie die zeichenfolgenformatierenden Zeichen (@, &amp;, \<, \> und !).</span><span class="sxs-lookup"><span data-stu-id="d7908-184">Examples of characters that can't be displayed as literal characters are the date-formatting and time-formatting characters (a, c, d, h, m, n, p, q, s, t, w, y, /, and :), the numeric-formatting characters (#, 0, %, E, e, comma, and period), and the string-formatting characters (@, &amp;, \<, \>, and !).</span></span>  <br/> |
|<span data-ttu-id="d7908-185">"ABC"</span><span class="sxs-lookup"><span data-stu-id="d7908-185">"ABC"</span></span>  <br/> |<span data-ttu-id="d7908-p117">Zeigt die Zeichenfolge zwischen den doppelten Anführungszeichen an (" "). Um eine Zeichenfolge im Formatargument innerhalb des Codes anzugeben, muss der Text mit Chr(34) umschlossen werden (34 ist der Zeichencode für ein Anführungszeichen (")).</span><span class="sxs-lookup"><span data-stu-id="d7908-p117">Displays the string inside the double quotation marks (" "). To include a string in the style argument within code, you must use Chr(34) to enclose the text (34 is the character code for a quotation mark (")).</span></span>  <br/> |
   
<span data-ttu-id="d7908-p118">Die folgende Tabelle enthält einige Beispiele für Zahlenformatausdrücke. (Bei diesen Beispielen wird davon ausgegangen, dass die Gebietsschemaeinstellung des Systems English-U.S. ist.) Die erste Spalte enthält die Formatierungszeichenfolgen für die Formatfunktion. Die anderen Spalten enthalten die resultierende Ausgabe, wenn die formatierten Daten den in der Spaltenüberschrift angegebenen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="d7908-p118">The following table contains some sample format expressions for numbers. (These examples all assume that your system's locale setting is English-U.S.) The first column contains the format strings for the Format function. The other columns contain the resulting output if the formatted data has the value given in the column headings.</span></span>
  
|<span data-ttu-id="d7908-191">**Format (Stil)**</span><span class="sxs-lookup"><span data-stu-id="d7908-191">**Format (Style)**</span></span>|<span data-ttu-id="d7908-192">**„5" formatiert als**</span><span class="sxs-lookup"><span data-stu-id="d7908-192">**"5" formatted as**</span></span>|<span data-ttu-id="d7908-193">**„-5" formatiert als**</span><span class="sxs-lookup"><span data-stu-id="d7908-193">**"-5" formatted as**</span></span>|<span data-ttu-id="d7908-194">**„0.5" formatiert als**</span><span class="sxs-lookup"><span data-stu-id="d7908-194">**"0.5" formatted as**</span></span>|<span data-ttu-id="d7908-195">**„0" formatiert als**</span><span class="sxs-lookup"><span data-stu-id="d7908-195">**"0" formatted as**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7908-196">Zeichnfolge der Länge Null ("")</span><span class="sxs-lookup"><span data-stu-id="d7908-196">Zero-length string ("")</span></span>  <br/> |<span data-ttu-id="d7908-197">5</span><span class="sxs-lookup"><span data-stu-id="d7908-197">5</span></span>  <br/> |<span data-ttu-id="d7908-198">-5</span><span class="sxs-lookup"><span data-stu-id="d7908-198">-5</span></span>  <br/> |<span data-ttu-id="d7908-199">0.5</span><span class="sxs-lookup"><span data-stu-id="d7908-199">0.5</span></span>  <br/> |<span data-ttu-id="d7908-200">0</span><span class="sxs-lookup"><span data-stu-id="d7908-200">0</span></span>  <br/> |
|<span data-ttu-id="d7908-201">0</span><span class="sxs-lookup"><span data-stu-id="d7908-201">0</span></span>  <br/> |<span data-ttu-id="d7908-202">5</span><span class="sxs-lookup"><span data-stu-id="d7908-202">5</span></span>  <br/> |<span data-ttu-id="d7908-203">-5</span><span class="sxs-lookup"><span data-stu-id="d7908-203">-5</span></span>  <br/> |<span data-ttu-id="d7908-204">1</span><span class="sxs-lookup"><span data-stu-id="d7908-204">1</span></span>  <br/> |<span data-ttu-id="d7908-205">0</span><span class="sxs-lookup"><span data-stu-id="d7908-205">0</span></span>  <br/> |
|<span data-ttu-id="d7908-206">0.00</span><span class="sxs-lookup"><span data-stu-id="d7908-206">0.00</span></span>  <br/> |<span data-ttu-id="d7908-207">5.00</span><span class="sxs-lookup"><span data-stu-id="d7908-207">5.00</span></span>  <br/> |<span data-ttu-id="d7908-208">-5.00</span><span class="sxs-lookup"><span data-stu-id="d7908-208">-5.00</span></span>  <br/> |<span data-ttu-id="d7908-209">0.50</span><span class="sxs-lookup"><span data-stu-id="d7908-209">0.50</span></span>  <br/> |<span data-ttu-id="d7908-210">0.00</span><span class="sxs-lookup"><span data-stu-id="d7908-210">0.00</span></span>  <br/> |
|<span data-ttu-id="d7908-211">#,##0</span><span class="sxs-lookup"><span data-stu-id="d7908-211">#,##0</span></span>  <br/> |<span data-ttu-id="d7908-212">5</span><span class="sxs-lookup"><span data-stu-id="d7908-212">5</span></span>  <br/> |<span data-ttu-id="d7908-213">-5</span><span class="sxs-lookup"><span data-stu-id="d7908-213">-5</span></span>  <br/> |<span data-ttu-id="d7908-214">1</span><span class="sxs-lookup"><span data-stu-id="d7908-214">1</span></span>  <br/> |<span data-ttu-id="d7908-215">0</span><span class="sxs-lookup"><span data-stu-id="d7908-215">0</span></span>  <br/> |
|<span data-ttu-id="d7908-216">$#,##0;($#,##0)</span><span class="sxs-lookup"><span data-stu-id="d7908-216">$#,##0;($#,##0)</span></span>  <br/> |<span data-ttu-id="d7908-217">$5</span><span class="sxs-lookup"><span data-stu-id="d7908-217">$5</span></span>  <br/> |<span data-ttu-id="d7908-218">($5)</span><span class="sxs-lookup"><span data-stu-id="d7908-218">($5)</span></span>  <br/> |<span data-ttu-id="d7908-219">$1</span><span class="sxs-lookup"><span data-stu-id="d7908-219">$1</span></span>  <br/> |<span data-ttu-id="d7908-220">$0</span><span class="sxs-lookup"><span data-stu-id="d7908-220">$0</span></span>  <br/> |
|<span data-ttu-id="d7908-221">$#,##0.00;($#,##0.00)</span><span class="sxs-lookup"><span data-stu-id="d7908-221">$#,##0.00;($#,##0.00)</span></span>  <br/> |<span data-ttu-id="d7908-222">$5.00</span><span class="sxs-lookup"><span data-stu-id="d7908-222">$5.00</span></span>  <br/> |<span data-ttu-id="d7908-223">($5.00)</span><span class="sxs-lookup"><span data-stu-id="d7908-223">($5.00)</span></span>  <br/> |<span data-ttu-id="d7908-224">$0.50</span><span class="sxs-lookup"><span data-stu-id="d7908-224">$0.50</span></span>  <br/> |<span data-ttu-id="d7908-225">$0.00</span><span class="sxs-lookup"><span data-stu-id="d7908-225">$0.00</span></span>  <br/> |
|<span data-ttu-id="d7908-226">0%</span><span class="sxs-lookup"><span data-stu-id="d7908-226">0%</span></span>  <br/> |<span data-ttu-id="d7908-227">500%</span><span class="sxs-lookup"><span data-stu-id="d7908-227">500%</span></span>  <br/> |<span data-ttu-id="d7908-228">-500%</span><span class="sxs-lookup"><span data-stu-id="d7908-228">-500%</span></span>  <br/> |<span data-ttu-id="d7908-229">50%</span><span class="sxs-lookup"><span data-stu-id="d7908-229">50%</span></span>  <br/> |<span data-ttu-id="d7908-230">0%</span><span class="sxs-lookup"><span data-stu-id="d7908-230">0%</span></span>  <br/> |
|<span data-ttu-id="d7908-231">0.00%</span><span class="sxs-lookup"><span data-stu-id="d7908-231">0.00%</span></span>  <br/> |<span data-ttu-id="d7908-232">500.00%</span><span class="sxs-lookup"><span data-stu-id="d7908-232">500.00%</span></span>  <br/> |<span data-ttu-id="d7908-233">-500.00%</span><span class="sxs-lookup"><span data-stu-id="d7908-233">-500.00%</span></span>  <br/> |<span data-ttu-id="d7908-234">50.00%</span><span class="sxs-lookup"><span data-stu-id="d7908-234">50.00%</span></span>  <br/> |<span data-ttu-id="d7908-235">0.00%</span><span class="sxs-lookup"><span data-stu-id="d7908-235">0.00%</span></span>  <br/> |
|<span data-ttu-id="d7908-236">0.00E+00</span><span class="sxs-lookup"><span data-stu-id="d7908-236">0.00E+00</span></span>  <br/> |<span data-ttu-id="d7908-237">5.00E+00</span><span class="sxs-lookup"><span data-stu-id="d7908-237">5.00E+00</span></span>  <br/> |<span data-ttu-id="d7908-238">-5.00E+00</span><span class="sxs-lookup"><span data-stu-id="d7908-238">-5.00E+00</span></span>  <br/> |<span data-ttu-id="d7908-239">5.00E-01</span><span class="sxs-lookup"><span data-stu-id="d7908-239">5.00E-01</span></span>  <br/> |<span data-ttu-id="d7908-240">0.00E+00</span><span class="sxs-lookup"><span data-stu-id="d7908-240">0.00E+00</span></span>  <br/> |
|<span data-ttu-id="d7908-241">0.00E-00</span><span class="sxs-lookup"><span data-stu-id="d7908-241">0.00E-00</span></span>  <br/> |<span data-ttu-id="d7908-242">5.00E00</span><span class="sxs-lookup"><span data-stu-id="d7908-242">5.00E00</span></span>  <br/> |<span data-ttu-id="d7908-243">-5.00E00</span><span class="sxs-lookup"><span data-stu-id="d7908-243">-5.00E00</span></span>  <br/> |<span data-ttu-id="d7908-244">5.00E-01</span><span class="sxs-lookup"><span data-stu-id="d7908-244">5.00E-01</span></span>  <br/> |<span data-ttu-id="d7908-245">0.00E00</span><span class="sxs-lookup"><span data-stu-id="d7908-245">0.00E00</span></span>  <br/> |
|<span data-ttu-id="d7908-246">"$#,##0;;\Z\e\r\o"</span><span class="sxs-lookup"><span data-stu-id="d7908-246">"$#,##0;;\Z\e\r\o"</span></span>  <br/> |<span data-ttu-id="d7908-247">$5</span><span class="sxs-lookup"><span data-stu-id="d7908-247">$5</span></span>  <br/> |<span data-ttu-id="d7908-248">$-5</span><span class="sxs-lookup"><span data-stu-id="d7908-248">$-5</span></span>  <br/> |<span data-ttu-id="d7908-249">$1</span><span class="sxs-lookup"><span data-stu-id="d7908-249">$1</span></span>  <br/> |<span data-ttu-id="d7908-250">Zero</span><span class="sxs-lookup"><span data-stu-id="d7908-250">Zero</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d7908-251">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7908-251">Remarks</span></span>
<span data-ttu-id="d7908-252"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="d7908-252"></span></span>

<span data-ttu-id="d7908-253">Wenn Sie Semikolons ohne Werte dazwischen einfügen, wird der fehlende Abschnitt mit dem Format des positiven Werts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7908-253">If you include semicolons with nothing between them, the missing section is displayed by using the format of the positive value.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7908-254">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7908-254">See also</span></span>

- [<span data-ttu-id="d7908-255">Format-Funktion (Access benutzerdefinierte Web app)</span><span class="sxs-lookup"><span data-stu-id="d7908-255">Format Function (Access custom web app)</span></span>](format-function-access-custom-web-app.md) 
- [<span data-ttu-id="d7908-256">Benutzerdefinierte Datums- und Uhrzeitformate für die Format-Funktion (benutzerdefinierte Access-Web-App)</span><span class="sxs-lookup"><span data-stu-id="d7908-256">Custom date and time formats for the Format function (Access custom web app)</span></span>](custom-date-and-time-formats-for-the-format-function-access-custom-web-app.md)
  
