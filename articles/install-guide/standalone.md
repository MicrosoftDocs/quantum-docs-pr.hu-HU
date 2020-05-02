---
title: 'Q # programok végrehajtása illesztőprogram és gazdagép nyelve nélkül'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706801"
---
# <a name="q-command-line-applications"></a>Q # parancssori alkalmazások

A Q # programok saját maguk is végrehajthatók a gazdagépen, például C#, F # vagy Python nyelven.

## <a name="pre-requisites"></a>Előfeltételek

- [.NET Core SDK 3,1 vagy újabb](https://www.microsoft.com/net/download)

## <a name="installation"></a>Telepítés

A Q # parancssori alkalmazásokat bármilyen IDE felépítheti, de a Q # alkalmazásaihoz kifejezetten ajánlott a Visual Studio Code (VS Code) vagy a Visual Studio IDE használata. A VS Code vagy a Visual Studio és a QDK Visual Studio Code bővítmény használatával gazdagabb funkciókhoz férhet hozzá.

- A [vs Code](https://code.visualstudio.com/download) telepítése (Windows, Linux és Mac)
- A [vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) -hoz készült QDK-bővítmény telepítése
- [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, a .NET Core platformfüggetlen fejlesztési tevékenységprofil engedélyezésével
- Töltse le és telepítse a [Visual Studio bővítményt](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)


## <a name="develop-with-q-using-vs-code"></a>Fejlesztés a Q # segítségével VS Code használatával

Telepítse a Quantum-projektsablonokat:

- Ugrás a **View** -> **parancs-paletta** megtekintéséhez
- Válassza a **Q #: Project-sablonok telepítése lehetőséget.**

Sikeresen telepítette a Quantum Development Kitet, amelyet mostantól felhasználhat az alkalmazásaiban és kódtáraiban.
- Hozzon létre egy új projektet:
  - Ugrás a **View** -> **parancs-paletta** megtekintéséhez
  - Válassza a **Q #: új projekt létrehozása** lehetőséget
  - **Önálló konzolos alkalmazás** kiválasztása
  - Lépjen arra a helyre a fájlrendszerben, ahol létre szeretné hozni az alkalmazást
  - A projekt elkészülte után kattintson az **Új projekt megnyitása...** gombra
        
- Vizsgálja meg a projektet
  - Látnia kell, hogy egy `Program.qs` létrehozott fájl egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.

- Futtassa az alkalmazást:
  - Ugrás a **terminál** -> **új terminálra**
  - Be`dotnet run`
  - A következőnek szövegnek kell megjelennie a kimeneti ablakban: `Hello quantum world!`


> [!NOTE]
> * A Visual Studio Code-bővítmény jelenleg nem támogatja a több gyökérmappával rendelkező munkaterületeket. Ha egy VS Code-munkaterületen belül több projekt is található, az összes projektnek azonos gyökérmappában kell lennie.

## <a name="develop-with-q-using-visual-studio"></a>Fejlesztés a Q # használatával a Visual Studióval

Ellenőrizze a telepítést egy `Hello World`-alkalmazás létrehozásával

- Hozzon létre egy új Q#-alkalmazást
  - Ugrás a **fájl** -> **új** -> **projektre**
  - A keresőmezőbe írja be a következőt: `Q#`
  - Válassza a **Q#-alkalmazás** elemet
  - Válassza a **tovább** lehetőséget
  - Válassza ki az alkalmazás nevét és helyét
  - **Létrehozás** kiválasztása

- Vizsgálja meg a projektet
  - Látnia kell, hogy egy nevű `Program.qs` fájl létre lett hozva, amely egy olyan Q # program, amely egy egyszerű műveletet határoz meg egy üzenetnek a konzolra való nyomtatásához.

- Az alkalmazás futtatása
  - Hibakeresési**kezdés kiválasztása hibakeresés nélkül** **Debug** -> 
  - Látni fogja, hogy a következő szöveg jelenik meg a konzolablakban: `Hello quantum world!`.

> [!NOTE]
> * Ha egy Visual Studio-megoldásban több projekt is található, a megoldásban foglalt összes projektnek a megoldás mappájában vagy valamelyik almappájában kell lennie.  


## <a name="whats-next"></a>A következő lépések

Most, hogy a választott környezetben telepítette a Quantum Development Kitet, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.write-program).
