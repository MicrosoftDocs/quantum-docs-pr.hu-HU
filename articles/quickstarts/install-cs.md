---
title: Fejlesztés Q#-pal és .NET-tel
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 24318380e0e63957a51961762a33446fe0121b21
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863669"
---
# <a name="develop-with-no-locq-and-net"></a>Fejlesztés Q#-pal és .NET-tel

A Q# úgy lett kifejlesztve, hogy jól együttműködjön a .NET-alapú nyelvekkel, például a C#-pal és az F#-pal.
Ebben az útmutatóban bemutatjuk, hogyan használhatja a Q#-ot egy .NET-nyelven írt gazdaprogrammal.

Először létrehozunk egy Q#-alkalmazást és egy .NET-gazdagépet, majd bemutatjuk, hogyan hívható meg a Q# a gazdagépről.

## <a name="prerequisites"></a>Előfeltételek

- Telepítse a [Q#-projektekhez készült](xref:microsoft.quantum.install.standalone) Quantum Development Kitet.

## <a name="creating-a-no-locq-library-and-a-net-host"></a>Q#-kódtár és .NET-gazdagép létrehozása

Első lépésként hozzon létre projekteket a Q#-kódtárhoz és a .NET-gazdagéphez, amely Q#-kódtárban definiált műveleteket és függvényeket hívja meg.

Kövesse a fejlesztési környezetéhez tartozó fülön található utasításokat.
Ha a Visual Studiótól vagy a VS Code-tól eltérő szerkesztőt használ, egyszerűen kövesse a parancssor lépéseit.

### <a name="visual-studio-code-or-command-prompt"></a>[Visual Studio Code vagy parancssor](#tab/tabid-cmdline)

- Új Q#-kódtár létrehozása

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- Hozzon létre egy új, C# vagy F# nyelvű konzolprojektet

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- Adja hozzá referenciaként a Q#-kódtárat a gazdaprogramból

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- [Opcionális] Hozzon létre megoldást mindkét projekthez

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

- Új Q#-kódtár létrehozása
  - Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez
  - A keresőmezőbe írja be a következőt: Q#
  - Válassza a **Q# Library (Q#-kódtár) lehetőséget**
  - Kattintson a **Tovább** gombra.
  - Adja meg a kódtár nevét és helyét
  - Győződjön meg arról, hogy a Place project and solution in same directory (Projekt és megoldás azonos kódtárba helyezése) beállítás **nincs bejelölve**
  - Kattintson a **Létrehozás** elemre.
- Hozzon létre egy új, C# vagy F# nyelvű gazdaprogramot
  - Lépjen a **File (Fájl)** → **New (Új)** → **Project (Projekt)** lehetőséghez
  - Válassza a Console App (.NET Core) Konzolalkalmazás (.NET Core) lehetőséget a C# vagy az F# esetében
  - Kattintson a **Tovább** gombra.
  - A *megoldás* alatt válassza az Add to solution (Hozzáadás a megoldáshoz) lehetőséget
  - Válasszon egy nevet a gazdaprogram számára
  - Kattintson a **Létrehozás** elemre.

***

## <a name="calling-into-no-locq-from-net"></a>A Q# meghívása a .NET-ből

Miután a fenti utasítások szerint beállította a projekteket, a .NET-konzolalkalmazásból meghívhatja a Q#-ot.
A Q#-fordító minden Q#-művelethez és -függvényhez .NET-osztályokat hoz létre, amelyek lehetővé teszik, hogy kvantumprogramokat futtathasson egy szimulátoron.

A [.NET-együttműködési minta](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) például a következő Q#-műveletet tartalmazza:

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

Ha ezt a műveletet .NET-ből szeretné meghívni egy kvantumszimulátoron, használhatja a Q#-fordító által létrehozott `RunAlgorithm` .NET-osztály `Run` metódusát:

### <a name="c"></a>[C#](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[F#](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a>További lépések

Most, hogy a Quantum Development Kit a Q#-alkalmazásokhoz, valamint a .NET-tel való együttműködéshez is be van állítva, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).
