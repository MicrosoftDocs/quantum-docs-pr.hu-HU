---
title: Alapszintű besorolás a Quantum Machine Learning könyvtárral
description: 'Megtudhatja, hogyan hajthat végre Q #-ban írt Quantum szekvenciális besorolást a Microsoft QDK Quantum Machine Learning könyvtára használatával.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: ddd889fdfabb505d7118c1eff551a6fbfa757309
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327645"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Alapszintű besorolás: adatok osztályozása a QDK

Ebből a rövid útmutatóból megtudhatja, hogyan hajthat végre Q #-ban írt Quantum szekvenciális osztályozó a QDK Quantum Machine learning könyvtára használatával. 

Ebben az útmutatóban a Half-moon adatkészletet fogjuk használni a Q #-ban definiált osztályozó szerkezet használatával.

## <a name="prerequisites"></a>Előfeltételek

- A Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Hozzon létre egy Q # projektet egy [Python-gazdagép](xref:microsoft.quantum.install.python) vagy egy [C#-gazda program](xref:microsoft.quantum.install.cs)számára.

## <a name="host-program"></a>Gazda program

A gazda program három részből áll:

- Töltse be az adatkészletet, és válassza ki a modell kezdő paramétereinek készletét.
- Képzés végrehajtása a modell paramétereinek és torzításának meghatározásához.
- A modell ellenőrzése a pontosság megállapításához

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Python a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-python)

    A Q # osztályozó a Pythonból való futtatásához mentse a következő kódot `host.py` . Ne feledje, hogy az `Training.qs` oktatóanyag későbbi részében ismertetett Q # fájlra is szüksége lesz.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Ezután a parancssorból futtathatja a Python-gazdaprogramot:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[C# a Visual Studio Code-dal vagy a parancssorból](#tab/tabid-csharp)

    A Q # osztályozó C#-ból való futtatásához mentse a következő kódot `Host.cs` . Ne feledje, hogy az `Training.qs` oktatóanyag későbbi részében ismertetett Q # fájlra is szüksége lesz.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ezután a parancssorból futtathatja a C#-gazdaprogramot:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[C# a Visual Studio 2019-cel](#tab/tabid-vs2019)

    Ha az új Q # programot C# nyelven szeretné futtatni a Visual Studióban, módosítsa `Host.cs` a következő C#-kód befoglalásával. Ne feledje, hogy az `Training.qs` oktatóanyag későbbi részében ismertetett Q # fájlra is szüksége lesz.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Ezután nyomja le az F5 billentyűt, így a program elkezdi a végrehajtást, és megjelenik egy új előugró ablak a következő eredményekkel: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# besorolási kód

Most nézzük meg, hogyan vannak meghatározva a gazda program által meghívott műveletek a Q #-ban.
A következő kódot menti egy nevű fájlba `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

A fenti kódban meghatározott legfontosabb funkciók és műveletek a következők:

- `ClassifierStructure() : ControlledRotation[]`: ebben a függvényben az áramköri modell felépítését úgy állítjuk be, hogy hozzáadja az ellenőrzött kapuk rétegeit. Ez a lépés egy szekvenciális, mélyebb tanulási modellben található neuronok rétegeinek deklarációját hasonlítja.
- `TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: Ez a művelet a kód legfontosabb része, és meghatározza a képzést. Itt betöltjük a mintákat a könyvtárban található adatkészletből, beállítjuk a Hyper-paramétereket és a betanítás kezdeti paramétereit, és elindítjuk a képzést a könyvtárban található művelet meghívásával `TrainSequentialClassifier` . Megjeleníti a paramétereket és a torzítást, amely meghatározza az osztályozó.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Ez a művelet meghatározza a modell kiértékelésének ellenőrzési folyamatát. Itt betöltjük a mintákat az ellenőrzéshez, a mintavételezések számát és a tűréshatárt. Az érvényesítéshez a kiválasztott kötegben a téves besorolások számát adja eredményül.

## <a name="next-steps"></a>Következő lépések

Először is játszhat a kóddal, és megpróbálhat módosítani néhány paramétert, hogy megtudja, hogyan befolyásolja a képzést. Ezután a következő oktatóanyagban [tervezze meg saját besorolását](xref:microsoft.quantum.libraries.machine-learning.design), és Ismerje meg, hogyan határozhatja meg az osztályozó szerkezetét.
