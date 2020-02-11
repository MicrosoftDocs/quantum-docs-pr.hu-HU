---
title: 'Fejlesztés a Q # +C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 7803846279f230f5fc0ee8424bd39be735a650ca
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036287"
---
# <a name="develop-with-q--c"></a>Fejlesztés a Q # +C#

Telepítse a QDK a Q C# # műveletek hívására szolgáló gazdagép-programok fejlesztéséhez.

A Q # a .NET-nyelvekkel jól játszható – konkrétan C#. Ezt a párosítást különböző fejlesztői környezetekben használhatja:

- [Q # + C# a Visual Studióval (Windows)](#VS)
- [Q # + C# Visual Studio Code használata (Windows, Linux és Mac)](#VSC)
- [Q # + C# a `dotnet` parancssori eszköz használata](#command)

## Fejlesztés a Q # + C# használatával a Visual Studióval <a name="VS"></a>

A Visual Studio sokoldalú környezetet kínál a Q # programok fejlesztéséhez. A Q # Visual Studio bővítmény a Q # fájlokhoz és projektekhez tartozó sablonokat, valamint a szintaxis kiemelését, a kód befejezését és az IntelliSense támogatását tartalmazza.


1. Előfeltételek

    - [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével

1. Telepítse a Q# Visual Studio-bővítményt

    - Töltse le és telepítse a [Visual Studio bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)

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

## Fejlesztés a Q # + C# eszközzel a Visual Studio Code használatával <a name="VSC"></a>

A Visual Studio Code (VS Code) sokoldalú környezetet kínál a Q # programok fejlesztéséhez Windows, Linux és Mac rendszereken.  A Q # VS Code bővítmény támogatja a Q # szintaxis kiemelését, a kód befejezését és a Q # kódrészleteket.

1. Előfeltételek

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3,1 vagy újabb](https://www.microsoft.com/net/download)

1. Telepítse a Quantum VS Code-bővítményt

    - Telepítse a [VS Code-bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)

1. Telepítse a Quantum-projektsablonokat:

   - Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
   - Válassza a **Q #: Project-sablonok telepítése lehetőséget.**

    Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Hozzon létre egy új projektet:

        - Lépjen a **Nézet** -> **Parancskatalógus** lehetőséghez
        - Válassza a **Q #: új projekt létrehozása** lehetőséget
        - **Önálló konzolos alkalmazás** kiválasztása
        - Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást
        - A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra

    - Ha még nincs telepítve a C# vs Code bővítmény, egy előugró ablak jelenik meg. Telepítse a bővítményt. 

    - Futtassa az alkalmazást:

        - Ugrás a **terminal** -> **új terminálra**
        - Adja meg `dotnet run`
        - A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`


> [!NOTE]
> * A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

## Fejlesztés a Q # + C# használatával a `dotnet` parancssori eszközzel <a name="command"></a>

Természetesen a parancssorból is egyszerűen összeállíthat és futtathat Q#-programokat, ha telepíti a .NET Core SDK-t és a QDK-projektsablonokat. 

1. Előfeltételek

    - [.NET Core SDK 3,1 vagy újabb](https://www.microsoft.com/net/download)

1. Telepítse a .NET-hez tartozó Quantum-projektsablonokat

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.

1. Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

    - Új alkalmazás létrehozása

       ```dotnetcli
       dotnet new console -lang "Q#" -o runSayHello
       ```

    - Lépjen az új alkalmazás könyvtárához

       ```bash
       cd runSayHello
       ```

    Látni fogja, hogy az alkalmazás projektfájljai mellett két fájl jött létre: egy Q#-fájl (`Operation.qs`) és egy C#-gazdafájl (`Driver.cs`).

    - Az alkalmazás futtatása

        ```dotnetcli
        dotnet run
        ```

        A következő kimenetnek kell megjelennie: `Hello quantum world!`

    
## <a name="whats-next"></a>A következő lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).
