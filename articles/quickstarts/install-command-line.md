---
title: Fejlesztés Q# nyelvű parancssori alkalmazásokkal
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871433"
---
# <a name="develop-with-q-command-line-applications"></a>Fejlesztés Q# nyelvű parancssori alkalmazásokkal

A Q#-programok külön, illesztő nélkül is végrehajthatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.

## <a name="prerequisites"></a>Előfeltételek

- [.NET Core SDK 3.1 vagy újabb verzió](https://www.microsoft.com/net/download)

## <a name="installation"></a>Telepítés

Bár Q# parancssori alkalmazásokat bármilyen IDE-ben létrehozhat, javasoljuk, hogy a Q#-alkalmazások helyi fejlesztéséhez használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t. A felhőben, webböngészőn keresztül történő fejlesztéshez a Visual Studio Codespaces használatát javasoljuk. Ha ezekben a környezetekben fejleszt, hozzáférhet a QDK-bővítmény széleskörű funkcióihoz, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket. 

A VS Code konfigurálása:

1. Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).
2. Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

A Visual Studio konfigurálása:

1. Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.
2. Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

A Visual Studio Codespaces konfigurálása:

1. Hozzon létre egy [Azure-fiókot](https://azure.microsoft.com/free/).
2. Hozzon létre egy Codespaces-környezetet. Kövesse a [gyorsútmutatót](https://docs.microsoft.com/visualstudio/online/quickstarts/browser). A Codespace létrehozásakor javasoljuk, hogy a QDK-specifikus beállítások betöltéséhez írja be a `microsoft/Quantum` elemet a „Git-adattár” mezőbe.
3. Most már elindíthatja az új környezetet, és megkezdheti a fejlesztést a böngészőben a [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments)használatával. Azt is megteheti, hogy a VS Code helyi telepítését használja, a Codespacest pedig [távoli környezetként](https://docs.microsoft.com/visualstudio/online/how-to/vscode) alkalmazza.


A QDK egy másik környezetben való telepítéséhez írja a következőt a parancssorba:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Fejlesztés a Q# használatával

Kövesse a környezetéhez tartozó fülön található utasításokat.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Új projekt létrehozása:

1. Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre, és válassza a **Q#: Create New Project (Q#: Új projekt létrehozása)** lehetőséget.
2. Kattintson a **Standalone console application (Különálló konzolalkalmazás)** elemre.
3. Keresse meg a projekt mentési helyét, majd kattintson a **Create Project (Projekt létrehozása)** lehetőségre.
4. A projekt sikeres létrehozását követően kattintson az **Open new project... (Új projekt megnyitása...)** lehetőségre a jobb alsó sarokban.
        
Vizsgálja meg a projektet. Látni fog egy `Program.qs` nevű forrásfájlt, amely egy olyan Q#-program, amely üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.

Az alkalmazás futtatása:
1. Kattintson a **Terminal (Terminál)**  -> **New Terminal (Új terminál)** elemre.
2. A terminál parancssorába írja be a következőt: `dotnet run`.
3. A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`


> [!NOTE]
> A VS Code Q#-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

Ellenőrizze a Visual Studio telepítését egy `Hello World` Q#-alkalmazás létrehozásával.

Új Q#-alkalmazás létrehozása:
1. Nyissa meg a Visual Studiót, majd kattintson a **File (Fájl)**  -> **New (Új)**  -> **Project (Projekt)** elemekre.
2. A keresőmezőbe írja be a következőt: `Q#`. Ezután válassza ki a **Q#-alkalmazást**, és kattintson a **Next (Tovább)** elemre.
3. Adja meg az alkalmazás nevét és helyét, majd kattintson a **Create (Létrehozás)** elemre.


Vizsgálja meg a projektet. Látni fog egy `Program.qs` nevű forrásfájlt, amely egy olyan Q#-program, amely üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja.

Az alkalmazás futtatása:
1. Válassza a **Debug (Hibakeresés)**  -> **Start Without Debugging (Indítás hibakeresés nélkül)** lehetőséget.
2. Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.

> [!NOTE]
> Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.  

### <a name="other-editors-with-the-command-line"></a>[Egyéb, parancssorral rendelkező szerkesztők](#tab/tabid-cmdline)

Ellenőrizze a telepítést egy `Hello World` Q#-alkalmazás létrehozásával.

1. Telepítse a projektsablonokat.

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. Új alkalmazás létrehozása:
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. Navigáljon az alkalmazás könyvtárához:
    ```dotnetcli
    cd runSayHello
    ```

    A könyvtár egy `Program.qs` nevű fájlt fog tartalmazni, amely egy olyan Q#-program, amely az üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja. Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival. 

1. Futtassa a programot:
    ```dotnetcli
    dotnet run
    ```

1. A következő szövegnek kell megjelennie: `Hello quantum world!`

***

## <a name="next-steps"></a>További lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
