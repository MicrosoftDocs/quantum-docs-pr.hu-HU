---
title: Fejlesztés Q# Jupyter-notebookokkal
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630331"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Fejlesztés Q# Jupyter-notebookokkal

A q # Jupyter Jegyzetfüzeteken a Q # műveletek fejlesztéséhez telepítse a QDK.

A Jupyter-jegyzetfüzetek lehetővé teszik a kód futtatását az utasítások, megjegyzések és egyéb tartalmak mellett. Ez a környezet ideális a Q # kód írására a beágyazott magyarázatokkal vagy a kvantum-számítástechnikai interaktív oktatóanyagokkal. Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.

Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.

> [!NOTE]
> * A Q # Jupyter jegyzetfüzetek esetében csak a Q # kód futtatható, és a műveletek nem hívhatók meg külső gazdagép-programokból (például Python vagy C# fájlokból). Ez a környezet nem megfelelő, ha a cél egy külső klasszikus gazda program összevonása a kvantum-programmal.

1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - [Jupyter notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Telepítse a(z) `iqsharp` csomagot

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

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Futtassa a következő parancsot a notebook-kiszolgáló elindításához:

        ```
        jupyter notebook
        ```

    - A Jupyter Notebook megnyitásához másolja és illessze be a parancssorban megadott URL-címet a böngészőjébe.

    - Hozzon létre egy Jupyter Notebook Q # kernelrel, és adja hozzá a következő kódot az első jegyzetfüzet-cellához:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Futtassa a notebook következő celláját:

        ![Jupyter Notebook cella Q # kóddal](~/media/install-guide-jupyter.png)

        A cella kimenetében a következőnek kell megjelennie: `SayHello`. Ha Jupyter Notebook fut, a Q # kód le lesz fordítva, és a jegyzetfüzet a megtalált művelet (ek) nevét adja meg.


    - Egy új cellában hajtsa végre az imént létrehozott műveletet (szimulátorban) a következő `%simulate` paranccsal:

        ![Jupyter Notebook cella% szimulálása mágia](~/media/install-guide-jupyter-simulate.png)

        A képernyőn megjelenő üzenetnek a meghívott művelet eredményével együtt kell megjelennie (itt látható az üres rekord, mert a `()` műveletünk egyszerűen egy `Unit` típust ad vissza).

## <a name="next-steps"></a>Következő lépések

Most, hogy telepítette a QDK a Q # Jupyter-jegyzetfüzetekhez, megírhatja és futtathatja [első Quantum programját](xref:microsoft.quantum.quickstarts.qrng) úgy, hogy a q # kódját közvetlenül a Jupyter notebook-környezetbe írja.

A Q # Jupyter notebookokkal kapcsolatos további példákért tekintse meg a következőt:
- [Bevezetés a Q # és a Jupyter notebookba](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/). Itt egy Q # Jupyter Notebook jelenik meg, amely bemutatja, hogyan használható a Q # ebben a környezetben.
- [Quantum katas](xref:microsoft.quantum.overview.katas), a saját ütemben elsajátított oktatóanyagok és a Q # Jupyter jegyzetfüzetek formájában elérhető programozási gyakorlatok gyűjteménye. A [Quantum katas oktatóanyagának notebookja](https://github.com/microsoft/QuantumKatas#tutorial-topics) jó kiindulási pont. A Quantum katas célja, hogy egy időben megtanítsa a Quantum Computing és a Q # programozási elemeit. Kiváló példa arra, hogy milyen típusú tartalmat hozhat létre a Q # Jupyter notebookokkal.
