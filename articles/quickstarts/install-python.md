---
title: Fejlesztés Q#-pal és Pythonnal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274084"
---
# <a name="develop-with-q-and-python"></a>Fejlesztés Q#-pal és Pythonnal

Telepítse a QDK-t a Python-gazdaprogramok fejlesztéséhez Q#-műveletek meghívása céljával.

1. Előfeltételek

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
  
1. Bár a Q#-ot bármilyen IDE-ben használhatja a Pythonnal, határozottan javasoljuk, hogy Q#- és Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t. A Visual Studio Code és a QDK Visual Studio Code-bővítmény használatával további funkciókhoz férhet hozzá.

    - A [VS Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)
    - Telepítse a [VS Code-hoz készült QDK-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - Hozzon létre egy `hello_world.py` nevű Python-programot a Q# `SayHello()` műveletének meghívásához:

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - Futtassa a programot:

        ```
        python hello_world.py
        ```

    - Ellenőrizze a kimenetet. A program kimenetében a következő soroknak kell szerepelniük:

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * Python Jupyter-notebookokat is használhat klasszikus Python programok írásához és Q#-műveletek cellákból való meghívásához. A Python-kód csak egy szokásos Python-program.

## <a name="next-steps"></a>További lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
