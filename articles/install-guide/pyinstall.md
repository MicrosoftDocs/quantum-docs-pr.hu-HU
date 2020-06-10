---
title: 'Fejlesztés Q # és Python nyelven'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630288"
---
# <a name="develop-with-q-and-python"></a>Fejlesztés Q # és Python nyelven

Telepítse a QDK a Python-gazdagépek kifejlesztéséhez a Q # műveleteinek meghívásához.

1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Telepítse a `qsharp` csomagot, amely egy Python-csomag, amely lehetővé teszi a Q # és a Python közötti együttműködési lehetőséget.

    ```
    pip install qsharp
    ```

1. Telepítse az IQ #, a Jupyter és a Python által használt kernelt, amely a Q # műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > Ha a lépés során hibaüzenet jelenik `dotnet iqsharp install` meg, nyisson meg egy új Terminálablak-ablakot, és próbálkozzon újra.
    > Ha ez továbbra sem működik, próbálja meg megkeresni a telepített `dotnet-iqsharp` eszközt (Windows rendszeren `dotnet-iqsharp.exe` ), és futtassa a következőt:
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > ahol a `/path/to/dotnet-iqsharp` fájlrendszerben lévő eszköz abszolút elérési útját kell cserélni `dotnet-iqsharp` .
    > Ez általában a `.dotnet/tools` felhasználói profil mappájában történik.
  
1. Habár a Q #-t bármilyen IDE-ben használhatja a Python használatával, javasoljuk, hogy a Q # + Python-alkalmazásokhoz használja a Visual Studio Code (VS Code) IDE-t. A Visual Studio Code és a QDK Visual Studio Code bővítmény használatával gazdagabb funkciókhoz férhet hozzá.

    - A [vs Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)
    - Telepítse a [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)-hoz készült QDK-bővítményt.

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
> * A Python Jupyter jegyzetfüzeteket is használhatja a klasszikus Python program írásához és a Q # műveletek a cellákból való meghívásához. A Python-kód csak egy normál Python-program.

## <a name="next-steps"></a>Következő lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
