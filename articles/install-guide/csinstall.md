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
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="a43ae-102">Q # használata C\# és F használatával\#</span><span class="sxs-lookup"><span data-stu-id="a43ae-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="a43ae-103">A Q # a .NET nyelvekkel, például a C# és az F # használatával készült.</span><span class="sxs-lookup"><span data-stu-id="a43ae-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="a43ae-104">Ebben az útmutatóban bemutatjuk, hogyan használható a Q # egy .NET nyelven írt gazda program használatával.</span><span class="sxs-lookup"><span data-stu-id="a43ae-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a43ae-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="a43ae-105">Prerequisites</span></span>

- <span data-ttu-id="a43ae-106">Telepítse a Quantum Development Kit [-t a Q # parancssori projektjeivel való használatra](xref:microsoft.quantum.install.standalone).</span><span class="sxs-lookup"><span data-stu-id="a43ae-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="a43ae-107">Q # könyvtár és egy .NET-gazdagép létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43ae-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="a43ae-108">Első lépésként hozzon létre projekteket a Q # Library-hez, illetve a .NET-gazdagéphez, amely a Q # Library-ben meghatározott műveleteket és függvényeket hívja meg.</span><span class="sxs-lookup"><span data-stu-id="a43ae-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="a43ae-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a43ae-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="a43ae-110">Új Q # könyvtár létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43ae-110">Create a new Q# library</span></span>
  - <span data-ttu-id="a43ae-111">Ugrás a **fájl** -> **új** -> **projektre**</span><span class="sxs-lookup"><span data-stu-id="a43ae-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="a43ae-112">Írja be a "Q #" kifejezést a keresőmezőbe</span><span class="sxs-lookup"><span data-stu-id="a43ae-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="a43ae-113">**Q # könyvtár** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a43ae-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="a43ae-114">Válassza a **tovább** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="a43ae-114">Select **Next**</span></span>
  - <span data-ttu-id="a43ae-115">A könyvtár nevének és helyének kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a43ae-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="a43ae-116">Győződjön meg arról, hogy a "Project és a megoldás elhelyezése ugyanabban a címtárban" nincs **bejelölve**</span><span class="sxs-lookup"><span data-stu-id="a43ae-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="a43ae-117">**Létrehozás** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a43ae-117">Select **Create**</span></span>
- <span data-ttu-id="a43ae-118">Új C# vagy F # gazda program létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43ae-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="a43ae-119">Nyissa meg a **fájl** → **új** → **projekt**</span><span class="sxs-lookup"><span data-stu-id="a43ae-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="a43ae-120">A "Console app (.NET Core") "kiválasztása C# vagy F esetén #</span><span class="sxs-lookup"><span data-stu-id="a43ae-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="a43ae-121">Válassza a **tovább** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="a43ae-121">Select **Next**</span></span>
  - <span data-ttu-id="a43ae-122">A *megoldás*területen válassza a "Hozzáadás a megoldáshoz" lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a43ae-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="a43ae-123">Válassza ki a gazda program nevét</span><span class="sxs-lookup"><span data-stu-id="a43ae-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="a43ae-124">**Létrehozás** kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a43ae-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="a43ae-125">Visual Studio Code vagy Command Line</span><span class="sxs-lookup"><span data-stu-id="a43ae-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="a43ae-126">Új Q # könyvtár létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43ae-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="a43ae-127">Új C# vagy F # konzol projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="a43ae-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="a43ae-128">Adja hozzá a Q # Library-t a gazda program hivatkozásához</span><span class="sxs-lookup"><span data-stu-id="a43ae-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="a43ae-129">Választható Megoldás létrehozása mindkét projekthez</span><span class="sxs-lookup"><span data-stu-id="a43ae-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="a43ae-130">A Q # hívása a .NET-ről</span><span class="sxs-lookup"><span data-stu-id="a43ae-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="a43ae-131">Miután beállította a projekteket a fenti utasítások követése után, meghívhatja a Q #-t a .NET-konzol alkalmazásából.</span><span class="sxs-lookup"><span data-stu-id="a43ae-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="a43ae-132">A Q # Compiler minden Q # művelethez és függvényhez hoz létre .NET-osztályokat, amelyek lehetővé teszik a kvantum-programok futtatását szimulátoron.</span><span class="sxs-lookup"><span data-stu-id="a43ae-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="a43ae-133">A .net-es [együttműködési minta](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) például egy Q # művelet következő példáját tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="a43ae-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="a43ae-134">Ha ezt a műveletet a .NET-keretrendszerben szeretné meghívni egy kvantum- `Run` szimulátoron, `RunAlgorithm` használhatja a Q # compiler által generált .net-osztály metódusát:</span><span class="sxs-lookup"><span data-stu-id="a43ae-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="a43ae-135">C #</span><span class="sxs-lookup"><span data-stu-id="a43ae-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="a43ae-136">F#</span><span class="sxs-lookup"><span data-stu-id="a43ae-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="a43ae-137">A következő lépések</span><span class="sxs-lookup"><span data-stu-id="a43ae-137">What's next?</span></span>

<span data-ttu-id="a43ae-138">Most, hogy már beállította a Quantum Development Kit-t mind a Q # parancssori programokhoz, mind a .NET-tel való együttműködéshez, megírhatja és futtathatja [az első kvantum-programot](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="a43ae-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
