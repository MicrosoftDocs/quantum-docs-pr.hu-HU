---
title: Fejlesztés Q# Jupyter-notebookokkal
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274095"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Fejlesztés Q# Jupyter-notebookokkal

Telepítse a QDK-t a Q#-műveletek Q# Jupyter-notebookokon történő fejlesztéséhez.

A Jupyter-notebookok helyszíni kódvégrehajtást tesznek lehetővé utasításokkal, megjegyzésekkel és egyéb tartalmakkal együtt. Ez a környezet megfelelő a beágyazott magyarázatokkal ellátott Q#-kód írásához vagy kvantum-számítástechnikai interaktív oktatóanyagokhoz. Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.

Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.

> [!NOTE]
> * A Q# Jupyter-notebookokban csak Q#-kódot futtathat, és a műveletek nem hívhatók meg külső gazdaprogramokból (pl. Python- vagy C#-fájlokból). Ez a környezet nem megfelelő, ha egy külső klasszikus gazdaprogrammal együtt szeretné használni a kvantumprogramot.

1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Telepítse a(z) `iqsharp` csomagot

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

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Futtassa a következő parancsot a notebook-kiszolgáló elindításához:

        ```
        jupyter notebook
        ```

    - A Jupyter Notebook megnyitásához másolja és illessze be a böngészőbe a parancssor által megadott URL-címet.

    - Hozzon létre egy Jupyter Notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Futtassa a notebook következő celláját:

        ![Jupyter Notebook-cella Q#-kóddal](~/media/install-guide-jupyter.png)

        A cella kimenetében a következőnek kell megjelennie: `SayHello`. A Jupyter Notebookban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.


    - Egy új cellában, a `%simulate` paranccsal hajtsa végre az imént létrehozott műveletet (szimulátorban):

        ![Jupyter Notebook-cella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

        A képernyőn megjelenik az üzenet a meghívott művelet eredményével együtt (ebben az esetben a `()` rekord üres, mert a művelet egyszerűen a `Unit` típust adja vissza).

## <a name="next-steps"></a>További lépések

Most, hogy telepítette a Q# Jupyter-notebookokhoz készült QDK-t, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng). Ehhez a Q#-kódot közvetlenül a Jupyter Notebook környezetben írhatja.

Az alábbi oktatóanyagokban talál további példákat arra, hogy mire használhatja még a Q# Jupyter-notebookokat:
- [A Q# és a Jupyter Notebook bemutatása](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Itt egy Q# Jupyter Notebook példáján mutatjuk be, hogyan használható a Q# ebben a környezetben.
- A [Kvantum Katák](xref:microsoft.quantum.overview.katas) saját ütemben elvégezhető oktatóanyagok és programozási gyakorlatok nyílt forráskódú gyűjteményei, Q# Jupyter-notebookok formájában. A [Kvantum Katák oktatóanyagban található notebookok](https://github.com/microsoft/QuantumKatas#tutorial-topics) jó kiindulási pontként szolgálnak. A Kvantum Katák célja a kvantum-számítástechnika elemeinek és a Q#-programozás egyidejű megismertetése. Remek példái annak, hogy milyen tartalmak hozhatók létre Q# Jupyter-notebookokkal.
