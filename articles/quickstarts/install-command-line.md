---
title: Fejlesztés Q# nyelvű parancssori alkalmazásokkal
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274122"
---
# <a name="develop-with-q-command-line-applications"></a>Fejlesztés Q# nyelvű parancssori alkalmazásokkal

A Q#-programok külön, illesztő nélkül is végrehajthatók olyan gazdanyelveken, mint például a C#, az F# vagy a Python.

## <a name="prerequisites"></a>Előfeltételek

- [.NET Core SDK 3.1 vagy újabb verzió](https://www.microsoft.com/net/download)

## <a name="installation"></a>Telepítés

Bár Q# parancssori alkalmazásokat bármilyen IDE-ben létrehozhat, javasoljuk, hogy Q#-alkalmazásokhoz használja a Visual Studio Code-ot (VS Code) vagy a Visual Studio IDE-t. Ha ezekben az eszközökben fejleszt, számos funkcióhoz férhet hozzá.

A VS Code konfigurálása:

1. Telepítse és töltse le a [VS Code-ot](https://code.visualstudio.com/download) (Windows, Linux és Mac).
2. Telepítse a [VS Code-hoz készült Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).

A Visual Studio konfigurálása:

1. Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3-as vagy újabb verzióját, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével.
2. Töltse le és telepítse a [Microsoft QDK-t](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Fejlesztés a Q# és a VS Code használatával

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

## <a name="develop-with-q-using-visual-studio"></a>Fejlesztés a Q# és a Visual Studio használatával

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


## <a name="next-steps"></a>További lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
