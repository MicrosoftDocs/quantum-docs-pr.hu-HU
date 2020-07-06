---
title: Fejlesztés Q#-pal és Pythonnal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 7fbbb81b1ee51bff74b287745bf4447004a0254c
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885528"
---
# <a name="develop-with-q-and-python"></a>Fejlesztés Q#-pal és Pythonnal

Telepítse a QDK-t a Python-gazdaprogramok fejlesztéséhez Q#-műveletek meghívása céljával.

## <a name="install-the-qsharp-python-package"></a>A(z) `qsharp` Python-csomag telepítése

### <a name="install-using-conda-recommended"></a>[Telepítés a Conda használatával (ajánlott)](#tab/tabid-conda)

1. Telepítse a [Miniconda](https://docs.conda.io/en/latest/miniconda.html) vagy [Anaconda](https://www.anaconda.com/products/individual#Downloads) telepítőt.

1. Nyisson meg egy Anaconda-parancssort.

   - Ha inkább a PowerShellt vagy a pwsh-t szeretné használni: nyisson meg egy rendszerhéjat, futtassa a `conda init powershell` parancsot, majd zárja be és nyissa meg újból a rendszerhéjat.

1. Az alábbi parancsok futtatásával hozzon létre és aktiváljon egy új Conda-környezetet `qsharp-env` néven a szükséges csomagokkal (beleértve a Jupyter Notebookot és az IQ#-ot):

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. A telepítés ellenőrzéséhez és a helyi csomaggyorsítótár valamennyi szükséges QDK-összetevővel való feltöltéséhez futtassa a `python -c "import qsharp"` parancsot ugyanarról a terminálról.

### <a name="install-using-net-cli-and-pip-advanced"></a>[Telepítés a .NET CLI és pip használatával (haladó)](#tab/tabid-dotnetcli)

1. Előfeltételek:

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Telepítse a `qsharp` Python-csomagot, amely lehetővé teszi a Q# és a Python közötti együttműködést.

    ```
    pip install qsharp
    ```

1. Telepítse az IQ#-ot, amely a Jupyter és a Python által használt kernel, és a Q#-műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.

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

Ennyi az egész! Most már a `qsharp` Python-csomag és a Jupyterhez tartozó IQ# kernel is telepítve van, amelyek a Q#-műveletek Pythonból való fordításához és végrehajtásához szükséges fő funkciókat biztosítják, és lehetővé teszik a Q# Jupyter-notebookok használatát.

## <a name="choose-your-ide"></a>Az IDE kiválasztása

Bár a Q#-ot bármilyen IDE-ben használhatja a Pythonnal, határozottan javasoljuk, hogy Q#- és Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t. A QDK Visual Studio Code-bővítmény használatával olyan további funkciókhoz férhet hozzá, mint a figyelmeztetések, a szintaxiselemek kiemelése, a projektsablonok és egyebek.

Ha a VS Code-ot szeretné használni:

- A [VS Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac).
- Telepítse a [VS Code-hoz készült QDK-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

Ha másik szerkesztőt szeretne használni, a fenti utasítások minden tudnivalót tartalmaznak.

## <a name="write-your-first-q-program"></a>Az első Q#-program megírása

Most már készen áll arra, hogy ellenőrizze a `qsharp` Python-csomag telepítését egy egyszerű Q#-program írásával és futtatásával.

1. Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. Az `Operation.qs` fájlt is tartalmazó mappában hozzon létre egy `host.py` nevű Python-programot a Q# `SampleQuantumRandomNumberGenerator()` műveletének szimulálásához:

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    SampleQuantumRandomNumberGenerator.simulate()
    ```

1. Futtassa a következő programot a telepítés során létrehozott környezetből (azaz a Conda vagy Python-környezetből, ahova a `qsharp`-ot telepítette):

    ```
    python host.py
    ```

1. Megjelenik a meghívott művelet eredménye. Mivel a művelet egy véletlenszerű eredményt hoz létre, ezért ebben az esetben a képernyőn a `Zero` vagy `One` érték jelenik meg. Ha újra és újra futtatja a programot, mindkét eredményt körülbelül az esetek felében fogja látni.

> [!NOTE]
> * A Python-kód csak egy szokásos Python-program. Python Jupyter-környezeteket, beleértve Python-alapú Jupyter-notebookokat is használhat klasszikus Python-programok írásához és Q#-műveletek meghívásához. A Python-program képes Q#-műveleteket importálni bármilyen olyan .qs fájlból, amely ugyanabban a mappában található, mint maga a Python-kód.

## <a name="next-steps"></a>További lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, ezen oktatóanyag segítségével megírhatja és futtathatja [első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
