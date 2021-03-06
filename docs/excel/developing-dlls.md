---
title: Entwickeln von DLLs
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- dlls [excel 2007], creating,creating DLLs [Excel 2007]
localization_priority: Normal
ms.assetid: 5d69d06d-a126-4c47-82ad-17112674c8a3
description: 'Gilt f�r: Excel 2013�| Office 2013�| Visual Studio'
ms.openlocfilehash: 030cdd4358d9a71841eca6acfcef6e71839e02a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790415"
---
# <a name="developing-dlls"></a>Entwickeln von DLLs

**Gilt für**: Excel 2013 | Office 2013 | Visual Studio 
  
Eine Bibliothek ist ein Textk�rper aus kompiliertem Code, der einige Funktionen sowie die Daten f�r eine ausf�hrbare Anwendung bereitstellt. Bibliotheken k�nnen entweder statisch verkn�pft oder dynamisch verkn�pft sein, und sie weisen in der Regel die Dateinamenerweiterung LIB bzw. DLL auf. Statische Bibliotheken (z. B. die C-Laufzeitbibliothek) werden bei der Kompilierung mit der Anwendung verkn�pft und werden so Teil der resultierenden ausf�hrbaren Datei. Die Anwendung l�dt eine DLL, wenn diese ben�tigt wird, in der Regel beim Start der Anwendung. Eine DLL-Datei kann eine weitere DLL laden und dynamisch mit dieser verkn�pft werden.
  
## <a name="benefits-of-using-dlls"></a>Vorteile der Verwendung von DLLs

Die Hauptvorteile von DLL-Dateien sind wie folgt:
  
- Alle Anwendungen k�nnen ein einzelnes Dokument auf der Festplatte gemeinsam verwenden.
    
- Die ausf�hrbaren Dateien von Anwendungen sind kleiner.
    
- Gro�e Entwicklungsprojekte k�nnen aufgeteilt werden. Anwendungs- und die DLL-Entwickler m�ssen sich nur auf eine Schnittstelle zwischen ihren jeweiligen Teilen einigen. Diese Schnittstelle wird von der DLL exportiert.
    
- DLL-Entwickler k�nnen DLLs aktualisieren � vielleicht, um sie effizienter zu gestalten oder um einen Fehler zu beheben � ohne, dass alle Anwendungen, die diese verwenden, aktualisiert werden m�ssen, vorausgesetzt, die exportierte Schnittstelle der DLL �ndert sich nicht.
    
Sie k�nnen DLLs verwenden, um Arbeitsblattfunktionen und Befehle in Microsoft Excel hinzuzuf�gen.
  
## <a name="resources-for-creating-dlls"></a>Ressourcen zum Erstellen von DLLs

Um eine DLL-Datei zu erstellen, ben�tigen Sie Folgendes:
  
- Einen Quellcode-Editor.
    
- Einen Compiler, um Quellcode in Objektcode umzuwandeln, der mit Ihrer Hardware kompatibel ist.
    
- Einen Linker, um Code aus statischen Bibliotheken hinzuzuf�gen, falls verwendet, und um die ausf�hrbare DLL-Datei zu erstellen.
    
Moderne integrierte Entwicklungsumgebungen, wie z. B. Microsoft Visual Studio, stellen all dies bereit. Sie bieten au�erdem noch viel mehr: intelligente Editoren, Tools zum Debuggen des Codes, Tools f�r die Verwaltung mehrerer Projekte, neue Projektassistenten und viele weitere wichtige Tools.
  
Sie k�nnen die DLL-Dateien in verschiedenen Sprachen erstellen, z. B. C/C++, Pascal und Visual Basic. Aufgrund der Tatsache, dass der in Excel bereitgestellte API-Quellcode C und C++ ist, werden in dieser Dokumentation nur diese beiden Sprachen ber�cksichtigt.
  
## <a name="exporting-functions-and-commands"></a>Exportieren von Funktionen und Befehle

Beim Kompilieren eines DLL-Projekts m�ssen der Compiler und der Linker wissen, welche Funktionen exportiert werden sollen, damit sie sie f�r die Anwendung verf�gbar machen k�nnen. Dieser Abschnitt beschreibt die Methoden hierf�r.
  
Wenn Compiler Quellcode kompilieren, �ndern sie in der Regel die Namen der Funktionen von deren Darstellung im Quellcode. Normalerweise erfolgt dies, indem etwas an den Anfang und/oder das Ende hinzugef�gt wird, ein Prozess, der als Namenserg�nzung bezeichnet wird. Sie m�ssen sicherstellen, dass die Funktion mit einem Namen exportiert wird, der f�r die Anwendung erkennbar ist, die die DLL l�dt. Dies kann bedeuten, dass der Linker angewiesen werden muss, dass der erg�nzte Name einem einfacheren Exportnamen zugeordnet wird. Der Exportname kann der Name sein, wie er urspr�nglich im Quellcode angezeigt wurde, oder ein anderer Name.
  
Wie der Name erg�nzt wird, h�ngt von der Sprache ab und davon, wie der Compiler angewiesen wird, die Funktion bereitzustellen, also von der Aufrufkonvention. Die standardm��ige Aufrufkonvention zwischen den Prozessen f�r Windows, die von DLL-Dateien verwendet wird, wird als WinAPI-Konvention bezeichnet. Sie ist in Windows-Headerdateien als **WINAPI** definiert, was wiederum mithilfe des Win32-Deklarators **__stdcall** definiert wird.
  
Eine DLL-Exportfunktion f�r die Verwendung mit Excel (ganz gleich, ob Arbeitsblattfunktion, Makrovorlagenfunktion oder benutzerdefinierter Befehl) sollte immer die Aufrufkonvention **WINAPI** / **__stdcall** verwenden. Der **WINAPI**-Bezeichner muss explizit in die Definition der Funktion eingeschlossen werden, da der Standard bei Win32-Compilern darin besteht, die **__cdecl**-Aufrufkonvention zu verwenden, die auch als **WINAPIV** definiert ist, wenn keine angegeben ist.
  
Sie haben mehrere M�glichkeiten, den Linker anzuweisen, dass eine Funktion exportiert werden soll, und ihm den Namen, unter dem diese extern bekannt sein soll, mitzuteilen:
  
- Platzieren Sie die Funktion in einer DEF-Datei nach dem **EXPORTS**-Schl�sselwort, und legen Sie die Einstellung Ihres DLL-Projekts so fest, dass beim Verkn�pfen auf diese Datei verwiesen wird. 
    
- Verwenden Sie den **__declspec(dllexport)**-Deklarator in der Definition der Funktion. 
    
- Verwenden Sie eine **#pragma**-Pr�prozessordirektive, um eine Nachricht an den Linker zu senden. 
    
Ihr Projekt kann zwar alle drei Methoden verwenden, und der Compiler und der Linken k�nnen diese unterst�tzen, Sie sollten jedoch nicht versuchen, eine Funktion auf mehrere Arten zu exportieren. Angenommen, dass eine DLL enthält zwei Quelle Codemodule, eine C und einer C++ die beiden Funktionen zu exportierenden enthalten, **Meine\_C\_exportieren** und **Meine\_Cpp\_exportieren** fest. Der Einfachheit halber nehmen wir an, dass jede Funktion ein einzelnes numerisches Argument mit doppelter Genauigkeit verwendet und denselben Datentyp zur�ckgibt. In den folgenden Abschnitten werden die alternativen für den Export von jede Funktion mit den einzelnen Methoden beschrieben. 
  
### <a name="using-a-def-file"></a>Verwenden einer DEF-Datei

```C
double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

```cpp
double WINAPI my_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

<br/>

Die DEF-Datei m�sste dann die folgenden Zeilen enthalten.
  
`EXPORTS my_C_export = _my_C_export@8  my_Cpp_export`

<br/>

Die allgemeine Syntax einer Zeile, die auf eine **EXPORTS**-Anweisung folgt, lautet folgenderma�en: 
  
`entryname[=internalname] [@ordinal[NONAME]] [DATA] [PRIVATE]`

Beachten Sie, dass die C-Funktion erg�nzt wurde, aber die DEF-Datei den Linker explizit zwingt, die Funktion mit dem Namen des urspr�nglichen Quellcodes verf�gbar zu machen (in diesem Beispiel). Der Linker exportiert die C++-Funktion implizit mit dem urspr�nglichen Codenamen, es ist daher nicht notwendig, den erg�nzten Namen in die DEF-Datei einzuschlie�en.
  
Bei 32-Bit-Windows-API-Funktionsaufrufen ist die Konvention f�r die Erg�nzung von C-kompilierten Funktionen wie folgt: **function_name** wird _ **function_name@** _n_, wobei  _n_ der Anzahl von Bytes entspricht, ausgedr�ckt als Dezimalzahl, die von allen Argumenten verwendet wird, und die Bytes jeweils auf das kleinste Vielfache von vier aufgerundet wurden. 
  
> [!NOTE]
> [!HINWEIS] Alle Zeiger weisen in Win32 eine Breite von vier Bytes auf. Der R�ckgabetyp hat keinen Einfluss auf die Namenserg�nzung. 
  
Der C++-Compiler kann gezwungen werden, nicht erg�nzte Namen f�r C++-Funktionen verf�gbar zu machen, indem die Funktion und alle Funktionsprototypen in einen externen �C" {�}-Block eingeschlossen werden, wie in diesem Beispiel gezeigt. (Die geschweiften Klammern **{}** werden hier ausgelassen, da die Deklaration nur auf den Funktionscodeblock Funktion verweist, der unmittelbar darauf folgt). 
  
```cpp
extern "C"
double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}

```

Wenn Sie C-Funktionsprototypen in Headerdateien platzieren, die in C- oder C++-Quelldateien eingeschlossen werden k�nnten, sollten Sie die folgende Pr�prozessordirektive einschlie�en.
  
```cpp
#ifdef __cplusplus
extern "C" {
#endif
double WINAPI my_C_export(double x);
double WINAPI my_Cdecorated_Cpp_export(double x);
#ifdef __cplusplus
}
#endif
```

### <a name="using-the-declspecdllexport-declarator"></a>Verwenden von __declspec(dllexport) declarator

Das **__declspec(dllexport)**-Schl�sselwort kann in der Deklaration der Funktion wie folgt verwendet werden. 
  
```cpp
__declspec(dllexport) double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

Das **__declspec(dllexport)**-Schl�sselwort am �u�ersten linken Rand der Deklaration hinzugef�gt werden. Die Vorteile dieses Ansatzes sind, dass die Funktion nicht unbedingt in einer DEF-Datei aufgelistet sein muss, und dass der Exportstatus mit der Definition richtig ist. 
  
Wenn Sie verhindern m�chten, dass eine C++-Funktion mit der C++-Namenserg�nzung verf�gbar gemacht wird, m�ssen Sie die Funktion wie folgt deklarieren.
  
```cpp
extern "C"
__declspec(dllexport) double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

Der Link macht die Funktion als �my_undecorated_Cpp_export" verf�gbar, d. h. mit dem Namen, wie er im Quellcode angezeigt wird, ohne Erg�nzung.
  
### <a name="using-a-pragma-preprocessor-linker-directive"></a>Mithilfe einer #pragma Präprozessor Linker-Direktive

Neuere Versionen von Microsoft Visual Studio unterst�tzen zwei vordefinierte Makros, die es in Verbindung mit einer **#pragma**-Direktive erm�glichen, den Linker anzuweisen, die Funktion direkt aus dem Funktionscode zu exportieren. Die Makros sind __FUNCTION__ und __FUNCDNAME__ (Beachten Sie den doppelten Unterstrich an jedem Ende), die zu den nicht erg�nzten bzw. erg�nzten Funktionsnamen erweitert werden. 
  
Wenn Sie z. B. Microsoft Visual Studio verwenden, k�nnen diese Zeilen wie folgt in eine gemeinsame Headerdatei integriert werden.
  
```cpp
#if _MSC_VER > 1200 // Later than Visual Studio 6.0
#define EXPORT comment(linker, "/EXPORT:"__FUNCTION__"="__FUNCDNAME__)
#else // Cannot use this way of exporting functions.
#define EXPORT
#endif // else need to use DEF file or __declspec(dllexport)

```

Wenn diese Kopfzeile in den Quelldateien enthalten ist, k�nnen die zwei Beispielfunktionen wie folgt exportiert werden.
  
C-Code:
  
```C
double WINAPI my_C_export(double x)
{
#pragma EXPORT
/* Modify x and return it. */
    return x * 2.0;
}
```

C++-Code:
  
```cpp
double WINAPI my_Cpp_export(double x)
{
#pragma EXPORT
// Modify x and return it.
    return x * 2.0;
}
```

Beachten Sie, dass die Direktive im Textk�rper der Funktion platziert werden muss und nur erweitert wird, wenn keine der Compileroptionen **/EP** oder **/P** festgelegt sind. Bei dieser Technik entf�llt die Notwendigkeit einer DEF-Datei oder **__declspec(dllexport)**-Deklaration, und die Angabe des Exportstatus verbleibt beim Funktionscode. 
  
## <a name="see-also"></a>Siehe auch

- [Zugriff auf DLLs in Excel](how-to-access-dlls-in-excel.md)
- [Aufrufen von Excel von der DLL oder XLL aus](calling-into-excel-from-the-dll-or-xll.md)
- [Excel-Programmierkonzepte](excel-programming-concepts.md)
- [Entwickeln von Excel-XLLs](developing-excel-xlls.md)

