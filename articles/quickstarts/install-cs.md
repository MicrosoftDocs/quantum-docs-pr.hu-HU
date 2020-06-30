---
title: Fejlesztés Q#-pal és .NET-tel
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274088"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="9d5ac-102">Fejlesztés Q#-pal és .NET-tel</span><span class="sxs-lookup"><span data-stu-id="9d5ac-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="9d5ac-103">A Q# úgy lett kifejlesztve, hogy a .NET-nyelvekkel, például C# és F#, jól együttműködjön.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="9d5ac-104">Ebben az útmutatóban bemutatjuk, hogyan használhatja a Q#-ot egy .NET-nyelven írt gazdaprogrammal.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d5ac-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="9d5ac-105">Prerequisites</span></span>

- <span data-ttu-id="9d5ac-106">Telepítse a [Q# parancssori projektekhez készült](xref:microsoft.quantum.install.standalone) Quantum Development Kitet.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="9d5ac-107">Q#-kódtár és .NET-gazdagép létrehozása</span><span class="sxs-lookup"><span data-stu-id="9d5ac-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="9d5ac-108">Első lépésként hozzon létre projekteket a Q#-kódtár és a .NET-gazdagép számára. Utóbbi a Q#-kódtárban definiált műveleteket és függvényeket hívja meg.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="9d5ac-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9d5ac-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="9d5ac-110">Új Q#-kódtár létrehozása</span><span class="sxs-lookup"><span data-stu-id="9d5ac-110">Create a new Q# library</span></span>
  - <span data-ttu-id="9d5ac-111">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="9d5ac-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="9d5ac-112">A keresőmezőbe írja be a Q# kifejezést</span><span class="sxs-lookup"><span data-stu-id="9d5ac-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="9d5ac-113">Válassza a **Q# Library (Q#-kódtár)** lehetőséget</span><span class="sxs-lookup"><span data-stu-id="9d5ac-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="9d5ac-114">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-114">Select **Next**</span></span>
  - <span data-ttu-id="9d5ac-115">Adja meg a kódtár nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="9d5ac-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="9d5ac-116">Győződjön meg arról, hogy a Place project and solution in same directory (Projekt és megoldás azonos kódtárba helyezése) beállítás **nincs bejelölve**</span><span class="sxs-lookup"><span data-stu-id="9d5ac-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="9d5ac-117">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-117">Select **Create**</span></span>
- <span data-ttu-id="9d5ac-118">Hozzon létre egy új, C# vagy F# nyelvű gazdaprogramot</span><span class="sxs-lookup"><span data-stu-id="9d5ac-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="9d5ac-119">Lépjen a **File (Fájl)** → **New (Új)** → **Project (Projekt)** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="9d5ac-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="9d5ac-120">Válassza a Console App (.NET Core) Konzolalkalmazás (.NET Core) lehetőséget a C# vagy az F# esetében</span><span class="sxs-lookup"><span data-stu-id="9d5ac-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="9d5ac-121">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-121">Select **Next**</span></span>
  - <span data-ttu-id="9d5ac-122">A *megoldás* alatt válassza az Add to solution (Hozzáadás a megoldáshoz) lehetőséget</span><span class="sxs-lookup"><span data-stu-id="9d5ac-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="9d5ac-123">Válasszon egy nevet a gazdaprogram számára</span><span class="sxs-lookup"><span data-stu-id="9d5ac-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="9d5ac-124">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="9d5ac-125">Visual Studio Code vagy parancssor</span><span class="sxs-lookup"><span data-stu-id="9d5ac-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="9d5ac-126">Új Q#-kódtár létrehozása</span><span class="sxs-lookup"><span data-stu-id="9d5ac-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="9d5ac-127">Hozzon létre egy új, C# vagy F# nyelvű konzolprojektet</span><span class="sxs-lookup"><span data-stu-id="9d5ac-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="9d5ac-128">Adja hozzá referenciaként a Q#-kódtárat a gazdaprogramból</span><span class="sxs-lookup"><span data-stu-id="9d5ac-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="9d5ac-129">[Opcionális] Hozzon létre megoldást mindkét projekthez</span><span class="sxs-lookup"><span data-stu-id="9d5ac-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="9d5ac-130">Meghívás Q#-ba .NET-ből</span><span class="sxs-lookup"><span data-stu-id="9d5ac-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="9d5ac-131">Miután beállította a projekteket a fenti utasítások követésével, meghívhat Q#-ba a .NET-konzolalkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="9d5ac-132">A Q#-fordító minden Q#-művelethez és -függvényhez .NET-osztályokat hoz létre, amelyek lehetővé teszik, hogy kvantumprogramokat futtathasson szimulátoron.</span><span class="sxs-lookup"><span data-stu-id="9d5ac-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="9d5ac-133">A [.NET-együttműködési minta](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) például a következő Q#-műveletet tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="9d5ac-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="9d5ac-134">Ha ezt a műveletet .NET-ből szeretné meghívni egy kvantumszimulátoron, használhatja a Q#-fordító által létrehozott `Run` .NET-osztály `RunAlgorithm` módszerét:</span><span class="sxs-lookup"><span data-stu-id="9d5ac-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="9d5ac-135">C#</span><span class="sxs-lookup"><span data-stu-id="9d5ac-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="9d5ac-136">F#</span><span class="sxs-lookup"><span data-stu-id="9d5ac-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="9d5ac-137">További lépések</span><span class="sxs-lookup"><span data-stu-id="9d5ac-137">Next steps</span></span>

<span data-ttu-id="9d5ac-138">Most, hogy a Quantum Development Kit mindkét Q# parancssori programhoz, valamint a .NET-tel való együttműködéshez is be van állítva, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="9d5ac-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
