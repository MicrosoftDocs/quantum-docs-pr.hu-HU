---
title: A saját keresési algoritmusának futtatása a Q# Quantum Development Kit-ben
description: Hozzon létre egy Q# projektet, amely bemutatja a a "a" és a "a" típusú, kanonikus algoritmusok egyikét.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5c23d71209eb484a510f102e8b581ba4ec21829a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869664"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Oktatóanyag: A keresési Grover-algoritmus implementálása Q#-ban\#

Ebből az oktatóanyagból megtudhatja, hogyan hozhat létre és futtathat Grover-keresést a strukturálatlan adatok keresésének felgyorsításához.  A a a legelterjedtebb kvantummechanika-algoritmusok egyike, és ez a viszonylag kis megvalósítás számos előnyt jelent a kvantum Q# -megoldások magas szintű kvantum-programozási nyelvvel való programozásának számos előnye, Q# hogy kifejezze a kvantum-algoritmusokat.  Az útmutató végén találja annak bemutatását, hogy a szimulációkimenet hogyan talál meg sikeresen egy sztringet egy rendezetlen bejegyzéslistában annak az időnek a töredéke alatt, amennyi a teljes lista klasszikus számítógépen történő áttekintéséhez kellene.

Grover algoritmusa egy strukturálatlan adatlistában keres bizonyos tételeket. Választ adhat például a következő kérdésre: A kártyapakliból húzott kártya egy kőr ász? Az adott tétel címkéjét _megjelölt bemenetnek_ hívják.

Grover keresési algoritmusát felhasználva egy kvantumszámítógép garantáltan kevesebb lépésből futtatja a keresést, mint ahány tételből áll a keresendő lista – erre egy átlagos algoritmus nem képes. A sebességnövekedés elhanyagolható egy kártyapakli esetében; több millió vagy több milliárd tételt tartalmazó listák esetében azonban már számottevő.

Grover keresési algoritmusát néhány sornyi kóddal megírhatja.

## <a name="prerequisites"></a>Előfeltételek

- A Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Mit csinál pontosan Grover keresési algoritmusa?

Grover algoritmusa rákérdez, hogy a lista egyik tétele az-e, amelyet keresünk. Ezt a lista indexeinek minden együtthatójára vagy valószínűségi amplitúdójára vetített kvantum-szuperpozíciójának összeállításával teszi, ami annak a valószínűségét mutatja, hogy az adott indexet keressük-e.

Az algoritmus mozgatórugója az a két lépés, ami fokozatosan növeli a keresett index együtthatóját, amíg az együttható valószínűségi amplitúdója el nem éri az egyet.

A fokozatos növekedések száma kevesebb, mint a lista tételeinek száma. Grover keresési algoritmusa ezért kevesebb lépésből hajtja végre a keresést, mint az átlagos algoritmusok.

![Grover keresési algoritmusának funkcionális diagramja](~/media/grover.png)

## <a name="write-the-code"></a>A kód írása

1. A Quantum Development Kit használatával [hozzon létre egy új Q# projektet a parancssori alkalmazáshoz](xref:microsoft.quantum.install.standalone). A projektnek adja a következő címet: `Grover`.

1. Az új projektjében adja a következő kódot az `Program.qs` fájlhoz:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. A keresendő lista meghatározásához hozzon létre egy új fájlt `Reflections.qs` néven, és illessze be a következő kódot:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    A `ReflectAboutMarked` művelet meghatározza az Ön által keresett megjelölt bemenetet, a nullák és egyek váltakozásából álló sztringet. Ez a minta szoftveresen rögzíti a megjelölt bemenetet, amely kiterjeszthető más bemenetek keresésére, vagy általánosítható bármilyen bemenetre.

1. Ezután futtassa az új Q# programot, és keresse meg a által megjelölt elemet `ReflectAboutMarked` .

### <a name="no-locq-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Q#Visual Studióval vagy Visual Studio Code-val rendelkező parancssori alkalmazások

A végrehajtható fájl a projekt konfigurációja és a parancssori lehetőségek függvényében egy szimulátoron vagy egy erőforrásbecslőn futtatja az `@EntryPoint()` attribútummal jelölt műveletet vagy függvényt.

A szkript végrehajtásához egyszerűen nyomja le a Ctrl + F5 billentyűkombinációt a Visual Studióban.

A VS Code-ban a `Program.qs` első alkalommal való összeállításához írja be az alábbiakat a terminálban:

```Command line
dotnet build
```

A későbbi futtatásokhoz az összeállítást nem kell megismételni. Futtatáshoz írja be a következő parancsot, majd nyomja le az Enter billentyűt:

```Command line
dotnet run --no-build
```

Ekkor a következő üzenetnek kell megjelennie a terminálon:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Ennek az az oka, hogy nem adta meg a használni kívánt qubitek számát, így a terminál kínálja fel a végrehajtható fájlhoz elérhető parancsokat. Ha 5 qubitet szeretnénk használni, a következőt írjuk be:

```Command line
dotnet run --n-qubits 5
```

Az Enter lenyomásakor a következő kimenetnek kell megjelennie:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>További lépések

Ha ezt az oktatóanyagot élvezte, tekintse meg az alábbi források némelyikét, ha többet szeretne megtudni arról, hogyan használható a Q# saját kvantum-alkalmazások írására:

- [Vissza a QDK-val való ismerkedésről szóló útmutatóhoz](xref:microsoft.quantum.welcome)
- Egy általánosabb [példa](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) a keresési Grover-algoritmusra
- [A Grover-kereséssel és a Kvantum Katákkal kapcsolatos további információk](xref:microsoft.quantum.overview.katas)
- További információk a Grover keresési algoritmusa mögött álló kvantum-számítástechnikai technikával, az [amplitúdó-erősítéssel][amplitude-amplification] kapcsolatban
- [Kvantum-számítástechnikai fogalmak](xref:microsoft.quantum.concepts.intro)
- [Példák a Quantum Development Kit használatára](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification
