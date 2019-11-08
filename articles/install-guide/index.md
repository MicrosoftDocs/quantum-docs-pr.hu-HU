---
title: A Microsoft Quantum Development Kit (QDK) telepítésének ismertetése
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 580ac14f2e839d723884a96e9c5fd336ebcb5da0
ms.sourcegitcommit: 30fcb35986b43388ad65dfb876eb3ad8ad0533ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73799160"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>A Microsoft Quantum Development Kit (QDK) telepítése

Ismerje meg a Microsoft Quantum Development Kit (QDK) telepítésének módját, hogy nekiláthasson a kvantumprogramozás első lépéseinek. A QDK a következőket tartalmazza:

- a Q# programozási nyelv
- kódtárak, amelyek összetett funkciókat választanak el a Q#-ban
- gazdaalkalmazás (Python vagy .NET nyelven írva), amely a Q# nyelven írt kvantumműveleteket futtatja
- a fejlesztést megkönnyítő eszközök

A választott fejlesztési környezettől függően a telepítés lépései eltérnek. Válassza ki a környezetet az alábbi szakaszok közül.

## <a name="develop-with-python"></a>Fejlesztés a Pythonnal

A Pythonhoz készült qsharp csomag megkönnyíti a Q#-műveletek és -függvények Pythonon belüli szimulálását. Az IQ# elsősorban a Jupyter és a Python által használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.

1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - A [PIP](https://pip.pypa.io/en/stable/installing) Python-csomagkezelő
    - [.NET Core SDK 3.0 vagy újabb verzió](https://www.microsoft.com/net/download)

1. Telepítse a(z) `qsharp` csomagot

    ```bash
    pip install qsharp
    ```

1. Telepítse a(z) `iqsharp` csomagot

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Hozzon létre egy minimális Q#-műveletet egy `Operation.qs` nevű fájl létrehozásával, majd adja hozzá a következő kódot:

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
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
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Fejlesztés a Jupyter-notebookokkal

Az oktatási területeken, tudományos laborokban és az internetes, együttműködése alapuló programozásban kedvenc Jupyter-notebookok helyszíni kódvégrehajtást tesznek lehetővé (most már Q#-kóddal is) utasításokkal, megjegyzésekkel és egyéb tartalmakkal együtt.  Az alábbiakat kell elvégeznie a saját Q#-notebookok létrehozásának megkezdéséhez.

Az IQ# elsősorban a Jupyter és a Python által a .NET Core SDK-hoz használt bővítmény, amely a Q#-műveletek összeállításának és szimulálásának alapvető funkcióit nyújtja.


1. Előfeltételek

    - [Python](https://www.python.org/downloads/) 3.6 vagy újabb verzió
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 vagy újabb verzió](https://www.microsoft.com/net/download)

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

    - Lépjen a parancssorban megjelenített URL-címre. Például: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Hozzon létre egy Jupyter-notebookot egy Q#-kernellel, majd szúrja be a következő kódot az első notebookcellába:

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Futtassa a notebook következő celláját:

        ![Jupyter-notebookcella Q#-kóddal](~/media/install-guide-jupyter.png)

        A cella kimenetében a következőnek kell megjelennie: `SayHello`. A Jupyter-notebookokban való futtatáskor a Q#-kód le lesz fordítva, és a notebook kiadja a talált művelet(ek) nevét.


    - Egy új cellában szimulálja a most létrehozott `%simulate`-művelet végrehajtását egy kvantumszámítógépen:

        ![Jupyter-notebookcella %simulate használatával](~/media/install-guide-jupyter-simulate.png)

        A képernyőn megjelenik az üzenet a meghívott művelet eredményével együtt (ebben az esetben üresen).


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Fejlesztés C#-pal Windows rendszeren, a Visual Studio használatával

A Visual Studio gazdag környezetet nyújt a Q#-programok fejlesztéséhez, nagyszerű funkciókkal, például kódkiegészítéssel és szintaxiskiemeléssel, amelyek végigvezetik a fejlesztőt az alkalmazások összeállításán.  A Q# Visual Studio-bővítmény Q#-fájlok és -projektek sablonjait, valamint szintaxiskiemelést és IntelliSense-támogatást tartalmaz.


1. Előfeltételek

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével

1. Telepítse a Q# Visual Studio-bővítményt

    - Töltse le a [Visual Studio-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)
    - Adja a bővítményt a Visual Studióhoz

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Hozzon létre egy új Q#-alkalmazást

        - Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez
        - A keresőmezőbe írja be a következőt: `Q#`
        - Válassza a **Q#-alkalmazás** elemet
        - Kattintson a **Tovább** gombra.
        - Válassza ki az alkalmazás nevét és helyét
        - Kattintson a **Létrehozás** elemre.

    - Vizsgálja meg a projektet

        Látni fogja, hogy két fájl jött létre: `Driver.cs`, amely a C#-gazdaalkalmazás, valamint `Operation.qs`, amely egy Q#-program, amely üzenetek a konzolon való megjelenítésének egyszerű műveletét definiálja.

    - Az alkalmazás futtatása

        - Válassza a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséget
        - Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.

> [!NOTE]
> * Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.  

## <a name="develop-with-c-using-visual-studio-code"></a>Fejlesztés C# nyelven a Visual Studio Code használatával

A Visual Studio Code (VS Code) gazdag környezetet nyújt a Q#-programok fejlesztéséhez számos különféle számítógépes környezethez, beleértve a Windows, Linux és Mac rendszereket, és nagyszerű funkciókat tartalmaz, például kódkiegészítést és szintaxiskiemelést, amelyek végigvezetik a fejlesztőt az alkalmazások összeállításán.  A Q# VS Code-bővítmény szintaxiskiemelést és Q#-kódrészleteket tartalmaz.

1. Előfeltételek

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 vagy újabb verzió](https://www.microsoft.com/net/download)

1. Telepítse a Quantum VS Code-bővítményt

    - Telepítse a [VS Code-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Telepítse a Quantum-projektsablonokat:

   - Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
   - Válassza a **Q#: Projektsablonok telepítése** lehetőséget

    Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Hozzon létre egy új projektet:

        - Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
        - Válassza a **Q#: Új projekt létrehozása** lehetőséget
        - Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást
        - A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra

    - Futtassa az alkalmazást:

        - Lépjen a **Hibakeresés** -> **Indítás hibakeresés nélkül** lehetőséghez
        - A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`

> [!NOTE]
> * > * A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>Fejlesztés a C# és a(z) `dotnet` parancssori eszköz használatával

Természetesen a parancssorból is egyszerűen összeállíthat és futtathat Q#-programokat, ha telepíti a .NET Core SDK-t és a QDK-projektsablonokat. 

1. Előfeltételek

    - [.NET Core SDK 3.0 vagy újabb verzió](https://www.microsoft.com/net/download)

1. Telepítse a .NET-hez tartozó Quantum-projektsablonokat

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Új alkalmazás létrehozása

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - Lépjen az új alkalmazás könyvtárához

       ```bash
       cd runSayHello
       ```

    Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).

    - Az alkalmazás futtatása

        ```bash
        dotnet run
        ```

        A következő kimenetnek kell megjelennie: `Hello quantum world!`

## <a name="whats-next"></a>A következő lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).
