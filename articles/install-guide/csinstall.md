---
title: Fejlesztés Q# + C# használatával
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680165"
---
# <a name="using-q-with-c-and-f"></a>Q # használata C\# és F használatával\#

A Q # a .NET nyelvekkel, például a C# és az F # használatával készült.
Ebben az útmutatóban bemutatjuk, hogyan használható a Q # egy .NET nyelven írt gazda program használatával.

## <a name="prerequisites"></a>Előfeltételek

- Telepítse a Quantum Development Kit [-t a Q # parancssori projektjeivel való használatra](xref:microsoft.quantum.install.standalone).

## <a name="creating-a-q-library-and-a-net-host"></a>Q # könyvtár és egy .NET-gazdagép létrehozása

Első lépésként hozzon létre projekteket a Q # Library-hez, illetve a .NET-gazdagéphez, amely a Q # Library-ben meghatározott műveleteket és függvényeket hívja meg.

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Új Q # könyvtár létrehozása
  - Ugrás a **fájl** -> **új** -> **projektre**
  - Írja be a "Q #" kifejezést a keresőmezőbe
  - **Q # könyvtár** kiválasztása
  - Válassza a **tovább** lehetőséget
  - A könyvtár nevének és helyének kiválasztása
  - Győződjön meg arról, hogy a "Project és a megoldás elhelyezése ugyanabban a címtárban" nincs **bejelölve**
  - **Létrehozás** kiválasztása
- Új C# vagy F # gazda program létrehozása
  - Nyissa meg a **fájl** → **új** → **projekt**
  - A "Console app (.NET Core") "kiválasztása C# vagy F esetén #
  - Válassza a **tovább** lehetőséget
  - A *megoldás*területen válassza a "Hozzáadás a megoldáshoz" lehetőséget.
  - Válassza ki a gazda program nevét
  - **Létrehozás** kiválasztása

### <a name="visual-studio-code-or-command-line"></a>[Visual Studio Code vagy Command Line](#tab/tabid-cmdline)

- Új Q # könyvtár létrehozása

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Új C# vagy F # konzol projekt létrehozása

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Adja hozzá a Q # Library-t a gazda program hivatkozásához

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- Választható Megoldás létrehozása mindkét projekthez

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a>A Q # hívása a .NET-ről

Miután beállította a projekteket a fenti utasítások követése után, meghívhatja a Q #-t a .NET-konzol alkalmazásából.
A Q # Compiler minden Q # művelethez és függvényhez hoz létre .NET-osztályokat, amelyek lehetővé teszik a kvantum-programok futtatását szimulátoron.

A .net-es [együttműködési minta](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) például egy Q # művelet következő példáját tartalmazza:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Ha ezt a műveletet a .NET-keretrendszerben szeretné meghívni egy kvantum- `Run` szimulátoron, `RunAlgorithm` használhatja a Q # compiler által generált .net-osztály metódusát:

### <a name="c"></a>[C #](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a>A következő lépések

Most, hogy már beállította a Quantum Development Kit-t mind a Q # parancssori programokhoz, mind a .NET-tel való együttműködéshez, megírhatja és futtathatja [az első kvantum-programot](xref:microsoft.quantum.write-program).
