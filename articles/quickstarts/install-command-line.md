---
title: Fejlesztés Q#-alkalmazásokkal egy IDE-ben
description: Megtudhatja, hogyan hozhat létre olyan Q#-alkalmazást, amely a parancssorból fut.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: a6823888dcbe8cf79f0045d2615fe8b889dcc7c3
ms.sourcegitcommit: a13c7c86fd52a05cbf129b8dd713d6586ca1cc2c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93376422"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a>Fejlesztés Q#-alkalmazásokkal egy IDE-ben

A Q#-programok külön, illesztő nélkül futtathatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python. Q#-alkalmazásokat a Visual Studio Code-ban (VS Code), a Visual Studióban, a Visual Studio Codespacesben vagy bármely szerkesztőben/IDE-ben is létrehozhat, és a .NET-konzolról futtathatja őket. 

## <a name="prerequisites-for-all-environments"></a>Az összes környezetre vonatkozó előfeltételek

- [.NET Core SDK 3.1 vagy újabb verzió](https://www.microsoft.com/net/download)

## <a name="installation"></a>Telepítés

Bár Q#-alkalmazásokat bármilyen IDE-ben buildelhet, javasoljuk, hogy a Q#-alkalmazások helyi fejlesztéséhez használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t. A felhőben, webböngészőn keresztül történő fejlesztéshez a Visual Studio Codespaces használatát javasoljuk. Ha ezekben a környezetekben fejleszt, kihasználhatja a QDK-bővítmény széles körű funkcióinak előnyeit, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket. 

### <a name="to-configure-for-vs-code"></a>Konfigurálás VS Code-hoz:

1. Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).
2. Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

### <a name="to-configure-for-visual-studio"></a>Konfigurálás Visual Studióhoz:

1. Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.
2. Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

### <a name="to-configure-for-another-environment"></a>Konfigurálás másik környezethez: 

1. Adja meg a következőt a parancssorban:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a>Konfigurálás Visual Studio Codespaceshez:

1. Hozzon létre egy [Azure-fiókot](https://azure.microsoft.com/free/).
2. Hozzon létre egy Codespaces-környezetet. Kövesse a [gyorsútmutatót](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser). A Codespace létrehozásakor javasoljuk, hogy a QDK-specifikus beállítások betöltéséhez írja be a `microsoft/Quantum` elemet a „Git-adattár” mezőbe.
3. Most már elindíthatja az új környezetet, és megkezdheti a fejlesztést a böngészőben a [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)használatával. Azt is megteheti, hogy a VS Code helyi telepítését használja, a Codespacest pedig [távoli környezetként](https://docs.microsoft.com/visualstudio/online/how-to/vscode) alkalmazza.

## <a name="develop-with-no-locq"></a>Fejlesztés a Q# használatával

Kövesse az alkalmazott fejlesztési környezetre vonatkozó fülön található utasításokat.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Új projekt létrehozása:

1. Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.
2. Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.
3. Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.
4. A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.

Vizsgálja meg a projektet. Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.

Az alkalmazás futtatása:

1. Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.
2. A terminál parancssorába írja be a következőt: `dotnet run`.
3. A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`

> [!NOTE]
> A VS Code Q#-bővítménye jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Ellenőrizze a Visual Studio telepítését egy Q# `Hello World`-alkalmazás létrehozásával.

Új Q#-alkalmazás létrehozása

1. Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.
2. A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást** , és kattintson a **Next (Tovább)** elemre.
3. Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.


Vizsgálja meg a projektet. Látni fog egy `Program.qs` nevű forrásfájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez.

Az alkalmazás futtatása:

1. Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.
2. Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.

> [!NOTE]
> Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.  

### <a name="other-editors-with-the-command-prompt"></a>[Egyéb, parancssorral rendelkező szerkesztők](#tab/tabid-cmdline)

Ellenőrizze a telepítést egy Q# `Hello World`-alkalmazás létrehozásával.

1. Új alkalmazás létrehozása:

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Navigáljon az alkalmazás könyvtárához:

    ```dotnetcli
    cd runSayHello
    ```

    A könyvtár tartalmaz egy `Program.qs` nevű fájlt. Ez egy Q#-program, amely egy egyszerű műveletet határoz meg az üzenetek konzolon való megjelenítéséhez. Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival. 

1. Futtassa a programot:

    ```dotnetcli
    dotnet run
    ```

1. A következő szövegnek kell megjelennie: `Hello quantum world!`

***

## <a name="next-steps"></a>További lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
