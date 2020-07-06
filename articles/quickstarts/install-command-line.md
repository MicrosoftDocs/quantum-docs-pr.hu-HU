---
title: Fejlesztés Q# nyelvű parancssori alkalmazásokkal
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884282"
---
# <a name="develop-with-q-command-line-applications"></a>Fejlesztés Q# nyelvű parancssori alkalmazásokkal

A Q#-programok külön, illesztő nélkül is végrehajthatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.

## <a name="prerequisites"></a>Előfeltételek

- [.NET Core SDK 3.1 vagy újabb verzió](https://www.microsoft.com/net/download)

## <a name="installation"></a>Telepítés

Bár Q# parancssori alkalmazásokat bármilyen IDE-ben létrehozhat, javasoljuk, hogy Q#-alkalmazásokhoz használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t. Ha ezekben a környezetekben fejleszt, hozzáférhet a QDK-bővítmény széleskörű funkcióihoz, beleértve a figyelmeztetéseket, a szintaxiselemek kiemelését, a projektsablonokat és egyebeket.

A VS Code konfigurálása:

1. Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).
2. Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

A Visual Studio konfigurálása:

1. Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.
2. Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).

A QDK egy másik környezetben való telepítéséhez írja a következőt a parancssorba:

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Fejlesztés a Q# használatával

Kövesse a környezetéhez tartozó fülön található utasításokat.

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

Telepítse a Q#-projektsablonokat:

1. Nyissa meg a VS Code-ot.
2. Kattintson a **View (Nézet)**  -> **Command Palette (Parancskatalógus)** elemre.
3. Válassza a **Q#: Install project templates (Q#: Projektsablonok telepítése)** lehetőséget.

A **projektsablonok sikeres telepítése esetén** jelenik meg, a QDK kész az Ön alkalmazásaival és kódtáraival való használatra.

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

1. Új alkalmazás létrehozása:
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. Navigáljon az alkalmazás könyvtárához:
    ```dotnetcli
    cd runSayHello
    ```

    A könyvtár egy `Program.qs` nevű fájlt fog tartalmazni, amely egy olyan Q#-program, amely az üzenetek konzolon való megjelenítésének egyszerű műveletét definiálja. Ezt a sablont egy szövegszerkesztővel módosíthatja, és felülírhatja saját kvantumalkalmazásaival. 

3. Futtassa a programot:
    ```dotnetcli
    dotnet run
    ```

4. A következő szövegnek kell megjelennie: `Hello quantum world!`

***

## <a name="next-steps"></a>További lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
