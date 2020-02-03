---
title: A keresési Grover-algoritmus futtatása Q#-ban – Quantum Development Kit
description: Állítson össze egy Q#-projektet, amely bemutatja a Grover-algoritmus, a bevett kvantumalgoritmusok egyikének működését.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: c1fd578fdb3d56a7b48972e6ccc9b1605047fe36
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820351"
---
# <a name="quickstart-implement-grovers-search-algorithm-in-q"></a>Gyorsútmutató: A keresési Grover-algoritmus implementálása Q#-ban

Ebből a gyorsútmutatóból megismerheti, hogyan hozhat létre és futtathat Grover-keresést a strukturálatlan adatok keresésének felgyorsításához.  A Grover-keresés az egyik legnépszerűbb kvantum-számítástechnikai algoritmus, és ebből a viszonylag kicsi Q#-implementációból megtapasztalhatja, hogy milyen előnyökkel jár a kvantummegoldások magas szintű Q# kvantumprogramozási nyelven történő programozása a kvantumalgoritmusok kifejezéséhez.  Az útmutató végén találja annak bemutatását, hogy a szimulációkimenet hogyan talál meg sikeresen egy sztringet egy rendezetlen bejegyzéslistában annak az időnek a töredéke alatt, amennyi a teljes lista klasszikus számítógépen történő áttekintéséhez kellene.

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

1. A Quantum Development Kit használatával [hozzon létre egy új Q#-projektet](xref:microsoft.quantum.howto.createproject)`Grover` néven az Ön által választott fejlesztői környezetben.

1. Az új projektjében adja a következő kódot az `Operations.qs` fájlhoz:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-23" highlight="5,27":::

1. A keresendő lista meghatározásához hozzon létre egy új fájlt `Reflections.qs` néven, és illessze be a következő kódot:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    A `ReflectAboutMarked` művelet meghatározza az Ön által keresett megjelölt bemenetet, a nullák és egyek váltakozásából álló sztringet. Ez a minta szoftveresen rögzíti a megjelölt bemenetet, amely kiterjeszthető más bemenetek keresésére, vagy általánosítható bármilyen bemenetre.

1. Ezután futtassa új Q#-programját a `ReflectAboutMarked` által jelölt tétel megtalálásához.

    ### <a name="python-with-visual-studio-code-or-the-command-linetabtabid-python"></a>[Python a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-python)

    Mentse `host.py`-ként a következő kódot az új Q#-program Pythonból történő futtatásához:

    :::code language="python" source="~/quantum/samples/algorithms/simple-grover/host.py" range="9-14":::

    Ezután a parancssorból futtathatja a Python-gazdaprogramot:

    ```bash
    $ python host.py
    Preparing Q# environment...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    [0, 1, 0, 1, 0]
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-linetabtabid-csharp"></a>[C# a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-csharp)

    Adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ből:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Ezután a parancssorból futtathatja a C#-gazdaprogramot:

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```

    ### <a name="c-with-visual-studio-2019tabtabid-vs2019"></a>[C# a Visual Studio 2019-cel](#tab/tabid-vs2019)

    A Visual Studióban adja hozzá a következő C#-kódot a `Driver.cs` fájlhoz, hogy futtatni tudja az új Q#-programot a C#-ból:

    :::code language="csharp" source="~/quantum/samples/algorithms/simple-grover/Host.cs" range="4-23":::

    Ezután nyomja le az F5 billentyűt, így a program elkezdi a végrehajtást, és megjelenik egy új előugró ablak a következő eredményekkel: 

    ```bash
    $ dotnet run
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Reflecting about marked state...
    Result: [Zero,One,Zero,One,Zero]

    Press any key to continue...
    ```
    ***

    A `ReflectAboutMarked` műveletet csak négyszer kellett lehívni, és a Q#-program képes volt megtalálni a „01010” bemenetet $2^{5} = 32$ lehetséges bemenet közül!

## <a name="next-steps"></a>További lépések

Ha hasznosnak találta ezt a gyorsútmutatót, tekintsen meg néhányat a lenti források közül, amelyek azzal foglalkoznak, hogyan írhat saját kvantumalkalmazásokat a Q# segítségével:

- [Vissza a QDK-val való ismerkedésről szóló útmutatóhoz](xref:microsoft.quantum.welcome)
- Egy általánosabb [példa](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) a keresési Grover-algoritmusra
- [A Grover-kereséssel és a Kvantum Katákkal kapcsolatos további információk](xref:microsoft.quantum.overview.katas)
- További információk a Grover keresési algoritmusa mögött álló kvantum-számítástechnikai technikával, az [amplitúdó-erősítéssel](xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification) kapcsolatban
- [Kvantum-számítástechnikai fogalmak](xref:microsoft.quantum.concepts.intro)
- [Példák a Quantum Development Kit használatára](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
