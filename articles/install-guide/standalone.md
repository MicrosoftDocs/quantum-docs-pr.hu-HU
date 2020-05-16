---
title: 'Fejlesztés Q # parancssori alkalmazásokkal'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426439"
---
# <a name="develop-with-q-command-line-applications"></a>Fejlesztés Q # parancssori alkalmazásokkal

A Q # programok saját maguk is végrehajthatók a gazdagépen, például C#, F # vagy Python nyelven.

## <a name="pre-requisites"></a>Előfeltételek

- [.NET Core SDK 3,1 vagy újabb](https://www.microsoft.com/net/download)

## <a name="installation"></a>Telepítés

A Q # parancssori alkalmazásai bármilyen IDE-ben létrehozhatók, de a Q # alkalmazásaihoz a Visual Studio Code (VS Code) vagy a Visual Studio IDE használata javasolt. Az ezekben az eszközökben való fejlesztés a sokoldalú funkciók elérését teszi lehetővé.

A VS Code konfigurálása:

1. Töltse le és telepítse a [vs Code](https://code.visualstudio.com/download) -ot (Windows, Linux és Mac).
2. Telepítse a [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)-hoz készült Microsoft-QDK.

A Visual Studio konfigurálása:

1. Töltse le és telepítse a [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16,3-es vagy újabb változatát, és engedélyezze a .net Core platformfüggetlen fejlesztési munkaterhelést.
2. Töltse le és telepítse a [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).


## <a name="develop-with-q-using-vs-code"></a>Fejlesztés a Q # segítségével VS Code használatával

A Q # Project-sablonok telepítése:

1. Nyissa meg a VS Code-ot.
2. Kattintson **View**a  ->  **parancs paletta**megtekintése elemre.
3. Válassza a **Q #: Project-sablonok telepítése**lehetőséget.

Ha a **Project templates telepítése sikeresen megtörtént** , a QDK készen áll a saját alkalmazásaival és könyvtáraival való használatra.

Új projekt létrehozása:

1. Kattintson **View**  ->  a**parancs paletta** megtekintése elemre, és válassza a **Q #: új projekt létrehozása**lehetőséget.
2. Kattintson a **különálló konzol alkalmazás**lehetőségre.
3. Navigáljon a projekt mentéséhez és a **projekt létrehozása**elemre.
4. A projekt sikeres létrehozása után kattintson a jobb alsó sarokban található **új projekt megnyitása..** . elemre.
        
Vizsgálja meg a projektet. Ekkor meg kell jelennie egy nevű forrásfájl `Program.qs` , amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.

Az alkalmazás futtatása:
1. Kattintson a **terminál**  ->  **új terminál**elemre.
2. A terminál parancssorába írja be a következőt: `dotnet run` .
3. A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`


> [!NOTE]
> A VS Code Q # bővítmény jelenleg nem támogatja a több legfelső szintű mappával rendelkező munkaterületek használatát. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

## <a name="develop-with-q-using-visual-studio"></a>Fejlesztés a Q # használatával a Visual Studióval

A Visual Studio telepítésének ellenőrzéséhez hozzon létre egy Q # `Hello World` alkalmazást.

Új Q #-alkalmazás létrehozása:
1. Nyissa meg a Visual studiót, és kattintson a **fájl**  ->  **új**  ->  **projekt**elemre.
2. Írja be `Q#` a keresőmezőbe a **Q # alkalmazás** elemet, és kattintson a **tovább**gombra.
3. Adja meg az alkalmazás nevét és helyét, majd kattintson a **Létrehozás**gombra.


Vizsgálja meg a projektet. Ekkor meg kell jelennie egy nevű forrásfájl `Program.qs` , amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.

Az alkalmazás futtatása:
1. Válassza a **hibakeresés**  ->  **indítása hibakeresés nélkül**lehetőséget.
2. Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.

> [!NOTE]
> Ha egy Visual Studio-megoldásban több projekt is van, a megoldásban szereplő összes projektnek ugyanabban a mappában kell lennie, mint a megoldásnak, vagy egy almappájában.  


## <a name="next-steps"></a>Következő lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
