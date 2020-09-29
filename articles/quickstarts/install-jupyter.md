---
title: Fejlesztés Q# Jupyter-notebookokkal
description: Megtudhatja, hogyan hozhat létre Q#-alkalmazásokat Jupyter-notebookok használatával.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51de510907ea087d1f23d3ff65d268d6d455a493
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834312"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a>Fejlesztés Q# Jupyter-notebookokkal

Telepítse a QDK-t a Q#-műveletek Q# Jupyter-notebookokon történő fejlesztéséhez.

A Jupyter-notebookok helyszíni kódszámítást tesznek lehetővé utasításokkal, megjegyzésekkel és egyéb tartalmakkal együtt. Ez a környezet megfelelő a beágyazott magyarázatokkal ellátott Q#-kód írásához vagy kvantum-számítástechnikai interaktív oktatóanyagokhoz. Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.

## <a name="install-the-ino-locq-jupyter-kernel"></a>Az IQ# Jupyter kernel telepítése

Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.

### <a name="install-using-conda-recommended"></a>[Telepítés a Conda használatával (ajánlott)](#tab/tabid-conda)

1. Telepítse a [Miniconda](https://docs.conda.io/en/latest/miniconda.html) vagy [Anaconda](https://www.anaconda.com/products/individual#Downloads) telepítőt. **Megjegyzés:** 64 bites telepítés szükséges.

1. Nyisson meg egy Anaconda-parancssort.

   - Ha inkább a PowerShellt vagy a pwsh-t szeretné használni: nyisson meg egy rendszerhéjat, futtassa a `conda init powershell` parancsot, majd zárja be és nyissa meg újból a rendszerhéjat.

1. Az alábbi parancsok futtatásával hozzon létre és aktiváljon egy új Conda-környezetet `qsharp-env` néven a szükséges csomagokkal (beleértve a Jupyter Notebookot és az IQ#-ot):

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. A telepítés ellenőrzéséhez és a helyi csomaggyorsítótár valamennyi szükséges QDK-összetevővel való feltöltéséhez futtassa a `python -c "import qsharp"` parancsot ugyanarról a terminálról.

### <a name="install-using-net-cli-advanced"></a>[Telepítés a .NET CLI használatával (haladó)](#tab/tabid-dotnetcli)

1. Előfeltételek:

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Telepítse az `Microsoft.Quantum.IQSharp` csomagot.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> Ha hibaüzenetet kap a `dotnet iqsharp install` lépés során, nyisson meg egy új terminálablakot, és próbálkozzon újra.
> Ha ez a lépés továbbra sem sikerül, keresse meg a telepített `dotnet-iqsharp` eszközt (Windows rendszeren: `dotnet-iqsharp.exe`), majd futtassa a következőt:
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> ahol a `/path/to/dotnet-iqsharp` helyére a fájlrendszerben található `dotnet-iqsharp` eszközre mutató abszolút elérési útvonalat kell beírni.
> Ez általában a `.dotnet/tools` területen található a felhasználó profil mappájában.
    
***

Ennyi az egész! Most már a Jupyterhez tartozó IQ# kernel is telepítve van, amely a Q#-műveletek Q# Jupyter-notebookokból való fordításához és futtatásához szükséges fő funkciókat biztosítja.

## <a name="create-your-first-no-locq-notebook"></a>Az első Q# notebook létrehozása

Most már készen áll arra, hogy ellenőrizze a Q# Jupyter-notebook telepítését egy egyszerű Q#-művelet írásával és futtatásával.

1. A Jupyter Notebook kiszolgáló indításához futtassa a következő programot a telepítés során létrehozott környezetből (azaz a létrehozott Conda-környezetből vagy a Python-környezetből, amelyben a Jupytert telepítette):

    ```
    jupyter notebook
    ```

    - Ha a Jupyter Notebook nem nyílik meg automatikusan a böngészőben, a megnyitásához másolja és illessze be a böngészőbe a parancssor által megadott URL-címet.

1. Válassza a **New (Új) → Q#** lehetőséget egy Jupyter-notebook létrehozásához egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Futtassa a notebook következő celláját:

    ![Jupyter notebookcella Q# kóddal](~/media/install-guide-jupyter.png)

    A cella kimenetében a következőnek kell megjelennie: `SampleQuantumRandomNumberGenerator`. A Jupyter-notebookban való futtatáskor a Q#-kód le lesz fordítva, és a cella kiadja a talált műveletek nevét.

1. Egy új cellában, a `%simulate` paranccsal futtassa az imént létrehozott műveletet (szimulátorban):

    ![Jupyter Notebook-cella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

    Megjelenik a meghívott művelet eredménye. Mivel a művelet egy véletlenszerű eredményt hoz létre, ezért ebben az esetben a képernyőn a `Zero` vagy `One` érték jelenik meg. Ha újra és újra futtatja a cellát, mindkét eredményt körülbelül az esetek felében fogja látni.

## <a name="next-steps"></a>További lépések

Most, hogy telepítette a Q# Jupyter-notebookokhoz készült QDK-t, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng). Ehhez a Q#-kódot közvetlenül a Jupyter-notebook környezetben írhatja.

Az alábbi oktatóanyagokban talál további példákat arra, hogy mire használhatja még a Q# Jupyter-notebookokat:

- [A Q# és a Jupyter Notebook bemutatása](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Itt egy Q# Jupyter-notebook példáján mutatjuk be, hogyan használható a Q# a Jupyter-környezetben.
- A [Kvantum Katák](xref:microsoft.quantum.overview.katas) saját ütemben elvégezhető oktatóanyagok és programozási gyakorlatok nyílt forráskódú gyűjteményei, Q# Jupyter-notebookok formájában. A [Kvantum Katák oktatóanyagban található notebookok](https://github.com/microsoft/QuantumKatas#tutorial-topics) jó kiindulási pontként szolgálnak. A Kvantum Katák célja a kvantum-számítástechnika elemeinek és a Q#-programozás egyidejű megismertetése. Remek példái annak, hogy milyen tartalmak hozhatók létre Q# Jupyter-notebookokkal.
