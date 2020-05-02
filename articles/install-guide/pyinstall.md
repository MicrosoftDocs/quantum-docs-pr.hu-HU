---
title: Fejlesztés Q# + Python használatával
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: e1b8a0c68b3ac0c059c6de6e478593321764ff88
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680150"
---
# <a name="develop-with-q--python"></a>Fejlesztés Q# + Python használatával

Telepítse a QDK a Python-gazdagépek kifejlesztéséhez a Q # műveleteinek meghívásához.

1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő
    - [.NET Core SDK 3,1 vagy újabb](https://www.microsoft.com/net/download)


1. Telepítse a `qsharp` csomagot, amely egy Python-csomag, amely lehetővé teszi a Q # és a Python közötti együttműködési lehetőséget.

    ```bash
    pip install qsharp
    ```

1. Telepítse az IQ #, a Jupyter és a Python által használt kernelt, amely a Q # műveletek fordításának és végrehajtásának alapvető funkcióit biztosítja.

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
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

        ```bash
        python hello_world.py
        ```

    - Ellenőrizze a kimenetet. A program kimenetében a következő soroknak kell szerepelniük:

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * A Python Jupyter jegyzetfüzeteket is használhatja a klasszikus Python program írásához és a Q # műveletek a cellákból való meghívásához. A Python-kód csak egy normál Python-program.

## <a name="whats-next"></a>A következő lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).
