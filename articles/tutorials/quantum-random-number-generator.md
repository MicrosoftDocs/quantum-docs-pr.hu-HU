---
title: Kvantum-véletlenszámgenerátor létrehozása
description: Hozzon létre egy olyan Q# projektet, amely az alapvető kvantum-fogalmakat, például a felépítést mutatja be egy kvantum véletlenszám-generátor létrehozásával.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8db892091794cb1166e41744572d8938d975abf2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869766"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>Oktatóanyag: Kvantum-véletlenszámgenerátor implementálása a Q#-ban\#

A-ben írt kvantum-algoritmus egyszerű példája Q# egy kvantum véletlenszám-generátor. Ez az algoritmus a kvantummechanika természetét használja ki egy véletlen szám előállításához.

## <a name="prerequisites"></a>Előfeltételek

- A Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Hozzon létre egy Q# projektet [ Q# a parancssorból](xref:microsoft.quantum.install.standalone)vagy egy [Python-gazda program](xref:microsoft.quantum.install.python) vagy [C#-gazda program](xref:microsoft.quantum.install.cs)használatával.

## <a name="write-a-no-locq-operation"></a>Művelet írása Q#

### <a name="no-locq-operation-code"></a>Q#műveleti kód

1. Cserélje le a Program.qs fájl tartalmát a következő kódra:

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

Ahogy azt [A kvantum-számítástechnika ismertetése](xref:microsoft.quantum.overview.understanding) című cikkben említettük, a qubit a kvantuminformáció egysége, amely szuperpozícióban lehet. Ha megmérjük, a qubit értéke csak 0 vagy 1 lehet. Végrehajtás során azonban a qubit állapota a 0 vagy 1 érték méréssel történő leolvasásának valószínűségét jelzi. Ezt a valószínűségi állapotot nevezzük szuperpozíciónak. E valószínűség segítségével generálhatunk véletlen számokat.

A Q# művelet során bemutatjuk a `Qubit` natív adattípust Q# . Egy `Qubit` csak a `using` utasítással foglalható le. Lefoglalás esetén a qubit mindig `Zero` állapotba kerül. 

A `H` művelet használatával a `Qubit` szuperpozícióba helyezhető. A qubit megméréséhez és értékének leolvasásához használja az `M` belső műveletet.

A `Qubit` szuperpozícióba történő helyezésekor és megmérésekor az eredmény más érték lesz a kód meghívásának minden alkalmával.

A `Qubit` lefoglalásának feloldásakor kifejezetten vissza kell állítani a `Zero` állapotba, máskülönben a szimulátor futásidejű hibát fog jelenteni. Ennek elérésére az egyik legegyszerűbb módszer a `Reset` meghívása.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>A kód vizualizálása a Bloch-gömbbel

A Bloch-gömbön az északi pólus a **0** klasszikus értéket jelöli, a déli pólus pedig az **1** klasszikus értéket. Minden szuperpozíció megadható a gömb egyik pontjaként (ezt a nyíl jelzi). Minél közelebb van a nyíl hegye a pólushoz, annál nagyobb a valószínűsége, hogy a qubit a mérésekor a pólushoz hozzárendelt klasszikus értékkel esik egybe. Az alábbi ábrán például a piros nyíllal jelölt qubitállapot esetében nagyobb a valószínűsége a **0** értéknek, ha megmérjük.

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

Ennek az ábrának a segítségével vizualizálhatjuk a kód működését:

* Először is egy **0** állapotban inicializált qubittel kezdünk, és a `H` alkalmazásával létrehozunk egy szuperpozíciót, amelyben a **0** és az **1** valószínűsége egyenlő.

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* Ezután megmérjük a qubitet, és mentjük a kimenetet:

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

A mérés eredménye teljesen véletlen, tehát egy véletlen bitből kaptuk meg. Ezt a műveletet többször is meghívhatjuk egész számok létrehozásához. Ha például háromszor hívjuk meg a műveletet, hogy három véletlen bitet kapjunk, véletlen hárombites számokat hozhatunk létre (tehát egy 0 és 7 közötti véletlen számot).


## <a name="creating-a-complete-random-number-generator"></a>Teljes körű véletlenszám-generátor létrehozása

Most, hogy egy Q# véletlenszerű bitet generáló művelettel rendelkezik, felhasználhatjuk egy teljes kvantum véletlenszám-generátor létrehozásához. Használhatjuk a Q# parancssori alkalmazásokat, vagy használhatunk egy gazda programot.



### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Q#Visual Studióval vagy Visual Studio Code-val rendelkező parancssori alkalmazások](#tab/tabid-qsharp)

A teljes Q# parancssori alkalmazás létrehozásához adja hozzá a következő belépési pontot a Q# programhoz: 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

A végrehajtható fájl a projekt konfigurációja és a parancssori lehetőségek függvényében egy szimulátoron vagy egy erőforrásbecslőn futtatja az `@EntryPoint()` attribútummal jelölt műveletet vagy függvényt.

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

A szkript végrehajtásához egyszerűen nyomja le a Ctrl + F5 billentyűkombinációt a Visual Studióban.

A VS Code-ban a Program.qs első alkalommal való összeállításához írja be az alábbiakat a terminálban:

```dotnetcli
dotnet build
```

A későbbi futtatásokhoz az összeállítást nem kell megismételni. Futtatáshoz írja be a következő parancsot, majd nyomja le az Enter billentyűt:

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-python)

Ha az új Q# programot a Pythonból szeretné futtatni, mentse a következő kódot `host.py` :

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

Ezután a parancssorból futtathatja a Python-gazdaprogramot:

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[C# Visual Studióval vagy Visual Studio Code-dal](#tab/tabid-csharp)

Az új Q# program c#-ból való futtatásához módosítsa `Driver.cs` a következő C#-kód befoglalását:

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

Ezután a parancssorból futtathatja a C#-gazdaprogramot (Visual Studióban nyomja le az F5 billentyűt):

```bash
$ dotnet run
The random number generated is 42
```

***
