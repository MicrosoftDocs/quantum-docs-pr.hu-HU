---
title: Kvantum-véletlenszámgenerátor létrehozása
description: Elkészíthet egy Q#-projektet, amely bemutatja az alapvető kvantumfogalmakat, például a kvantum-véletlenszámgenerátor létrehozása általi szuperpozíciót.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906984"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Gyorsútmutató: Kvantum-véletlenszámgenerátor implementálása a Q#-ban
A Q#-ban írt kvantumalgoritmusok egyik egyszerű példája egy kvantum-véletlenszámgenerátor. Ez az algoritmus a kvantummechanika természetét használja ki egy véletlen szám előállításához. 

## <a name="prerequisites"></a>Előfeltételek

- A Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Q#-projekt létrehozása](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Q#-művelet írása

### <a name="q-operation-code"></a>Q#-műveletkód

1. Cserélje le az Operation.qs fájl tartalmát a következő kódra:

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

Ahogy a [Mi az a kvantum-számítástechnika?](xref:microsoft.quantum.overview.what) című cikkben említettük, a qubit a kvantuminformáció egysége, amely szuperpozícióban lehet. Ha megmérjük, a qubit értéke csak 0 vagy 1 lehet. Végrehajtás során azonban a qubit állapota a 0 vagy 1 érték méréssel történő leolvasásának valószínűségét jelzi. Ezt a valószínűségi állapotot nevezzük szuperpozíciónak. E valószínűség segítségével generálhatunk véletlen számokat.

A Q#-műveletben bevezetjük a Q#-ban natív `Qubit` adattípust. Egy `Qubit` csak a `using` utasítással foglalható le. Lefoglalás esetén a qubit mindig `Zero` állapotba kerül. 

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

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>Teljes körű véletlenszám-generátor létrehozása egy gazdaprogrammal

Most, hogy rendelkezünk egy olyan Q#-művelettel, amely véletlenszerű biteket generál, felhasználhatjuk egy teljes kvantum-véletlenszámgenerátor összeállítására egy gazdaprogrammal.

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-python)
 
 Mentse `host.py`-ként a következő kódot az új Q#-program Pythonból történő futtatásához:
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 Ezután a parancssorból futtathatja a Python-gazdaprogramot:
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-csharp)
 
 Adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ből:
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 Ezután a parancssorból futtathatja a C#-gazdaprogramot:
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[C# a Visual Studio 2019-cel](#tab/tabid-vs2019)

 A Visual Studióban adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ból:

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 Ezután nyomja le az F5 billentyűt, így a program elkezdi a végrehajtást, és megjelenik egy új előugró ablak a létrehozott véletlenszerű számmal: 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
