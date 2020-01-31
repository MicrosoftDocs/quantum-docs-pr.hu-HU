---
title: 'Megtudhatja, hogyan hozhat létre Q # projektet a Quantum Development Kit (QDK) használatával'
description: 'A QDK és a Q # értékkel rendelkező projekt inicializálásával kiválaszthatja az Ön által választott fejlesztési környezetet'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 5fa32f14291fa2070b49e4bb3b720cbf31ee614b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819892"
---
# <a name="create-a-q-project-in-your-development-environment"></a>Q # projekt létrehozása a fejlesztői környezetben

Megtudhatja, hogyan hozhat létre Q # projektet a QDK.

A Q # projekt a kvantum-kódot tartalmazó Q # fájlokat, valamint a Quantum program futtatására szolgáló gazda programot tartalmaz. A gazda programot .NET-nyelveken C#, például a (z) vagy a Pythonban is megírhatja. A Q # kódot egy Jupyter-jegyzetfüzetben is futtathatja az IQ # kernel használatával.

Válassza ki a fejlesztési környezetét és nyelvét az alábbi fejezetekben:

* [Python](#create-a-python-project)
* [Q # Jupyter notebookok](#create-a-q-jupyter-notebook-project)
* [C#a Visual Studióval](#create-a-c-project-on-windows-using-visual-studio)
* [C#VS Code-val](#create-a-c-project-using-vs-code)
* [C#a parancssorral](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Python-projekt létrehozása

1. Előfeltételek

     * A [Pythonhoz készült Quantum Development Kit](xref:microsoft.quantum.install.python) telepítése

1. Hozzon létre egy mappát a projekt számára, és navigáljon a mappára

1. Hozzon létre egy `Operation.qs`nevű Q # fájlt, és adja hozzá a Q # kódját. Példa:

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Hozzon létre egy `host.py` nevű Python-gazdagépet a Q # művelet meghívásához. Példa:

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. Futtassa a programot:

    ```bash
    python host.py
    ```

1. Ellenőrizze a kimenetet. A program kimenetében a következő soroknak kell szerepelniük:

    ```bash
    Hello from quantum world!
    0
    ```

Most már folytathatja a kvantum-program fejlesztését.

## <a name="create-a-q-jupyter-notebook-project"></a>Q # Jupyter Notebook projekt létrehozása

1. Előfeltételek

    * A [Quantum Development Kit telepítése Jupyter notebookokhoz](xref:microsoft.quantum.install.jupyter)

1. Futtassa a következő parancsot a notebook-kiszolgáló elindításához:

    ```bash
    jupyter notebook
    ```

1. Lépjen a parancssorban megjelenített URL-címre. Például: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Megjelenik egy Jupyter lap a böngészőben. A **Files (fájlok** ) lapon válassza az **új** > **q #** lehetőséget, hogy Jupyter-jegyzetfüzetet hozzon létre a q # kernel használatával. Adja hozzá a következő kódot az első jegyzetfüzet-cellához:

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. Válassza a **cella** > a **cellák futtatása** lehetőséget a jegyzetfüzet futtatásához. `SayHello` hamarosan megjelennek a cella kimenetében:

    ![Jupyter-notebookcella Q#-kóddal](~/media/install-guide-jupyter.png)

    Jupyter-jegyzetfüzetekben való futtatáskor a Q # kód le van fordítva, és a jegyzetfüzet a megtalált művelet (ek) nevét adja meg.

1. Egy új cellában szimulálja a most létrehozott `%simulate`-művelet végrehajtását egy kvantumszámítógépen:

    ![Jupyter-notebookcella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

    A képernyőn megjelenik az üzenet a meghívott művelet eredményével együtt (ebben az esetben üresen).

Mostantól további Q #-műveleteket is hozzáadhat a kvantum-fejlesztés folytatásához.

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>C# Projekt létrehozása Windows rendszeren a Visual Studio használatával

1. Előfeltételek

    * A [Quantum Development Kit bővítmény telepítése a Visual studióhoz](xref:microsoft.quantum.install.cs)

1. Hozzon létre egy új Q#-alkalmazást

    * Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez
    * A keresőmezőbe írja be a következőt: `Q#`
    * Válassza a **Q#-alkalmazás** elemet
    * Kattintson a **Tovább** gombra.
    * Válassza ki az alkalmazás nevét és helyét
    * Kattintson a **Létrehozás** elemre.

1. Vizsgálja meg a projektet

    Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.

1. Az alkalmazás futtatása

    * Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget
    * Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.

Most már folytathatja a kvantum-fejlesztést a Visual Studio használatával

> [!NOTE]
> * Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.  

## <a name="create-a-c-project-using-vs-code"></a>Projekt létrehozása C# a vs Code használatával

1. Előfeltételek

    * A [Quantum Development Kit bővítmény telepítése a vs Code](xref:microsoft.quantum.install.cs) -hoz

1. Hozzon létre egy új projektet:

    * Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
    * Válassza a **Q #: új projekt létrehozása** lehetőséget
    * **Önálló konzolos alkalmazás** kiválasztása
    * Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást
    * A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra

1. Futtassa az alkalmazást:

    * Ugrás a **terminal** -> **új terminálra**
    * Adja meg `dotnet run`
    * A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`

Most már folytathatja a kvantum-fejlesztést a Visual Studio Code használatával.

> [!NOTE]
> * A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>C# Projekt létrehozása a `dotnet` parancssori eszköz használatával

1. Előfeltételek

    * A [Quantum Development Kit telepítése a parancssorba](xref:microsoft.quantum.install.cs)

1. Új alkalmazás létrehozása

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. Lépjen az új alkalmazás könyvtárához

    ```bash
    cd <project name>
    ```

    Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).

1. Az alkalmazás futtatása

    ```bash
    dotnet run
    ```

    A következő kimenetnek kell megjelennie: `Hello quantum world!`

Most folytassa a kvantum-fejlesztést a parancssori eszközök használatával.

## <a name="whats-next"></a>Vajon mi a következő lépés?

Most, hogy létrehozott egy projektet az előnyben részesített környezetben, folytathatja a kvantum-fejlesztést.
