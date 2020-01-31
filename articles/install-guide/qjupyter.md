---
title: 'Fejlesztés Q # Jupyter notebookokkal'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831069"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Fejlesztés Q # Jupyter notebookokkal

A q # Jupyter Jegyzetfüzeteken a Q # műveletek fejlesztéséhez telepítse a QDK.

A Jupyter-jegyzetfüzetek lehetővé teszik a kód futtatását az utasítások, megjegyzések és egyéb tartalmak mellett. Ez a környezet ideális a Q # kód írására a beágyazott magyarázatokkal vagy a kvantum-számítástechnikai interaktív oktatóanyagokkal. Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.

Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.

> [!NOTE]
> * A Q # Jupyter jegyzetfüzetek esetében csak a Q # kód futtatható, és a műveletek nem hívhatók meg külső gazdagép-programokból (például Pythonból vagy C# fájlokból). Ez a környezet nem megfelelő, ha a cél egy külső klasszikus gazda program összevonása a kvantum-programmal.

1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1 vagy újabb](https://www.microsoft.com/net/download)

1. Telepítse a(z) `iqsharp` csomagot

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Futtassa a következő parancsot a notebook-kiszolgáló elindításához:

        ```bash
        jupyter notebook
        ```

    - Nyissa meg a Jupyter jegyzetfüzetet, és illessze be a parancssorban megadott URL-címet a böngészőjébe.

    - Hozzon létre egy Jupyter-notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Futtassa a notebook következő celláját:

        ![Jupyter-notebookcella Q#-kóddal](~/media/install-guide-jupyter.png)

        A cella kimenetében a következőnek kell megjelennie: `SayHello`. A Jupyter-notebookokban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.


    - Egy új cellában hajtsa végre az imént létrehozott műveletet (szimulátorban) a `%simulate` parancs használatával:

        ![Jupyter-notebookcella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

        Ekkor meg kell jelennie a képernyőn kinyomtatott üzenetnek a meghívott művelet eredményével együtt (itt látható az üres rekord `()`, mert a művelet egyszerűen visszaadja a `Unit` típusát).

## <a name="whats-next"></a>Vajon mi a következő lépés?

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).
