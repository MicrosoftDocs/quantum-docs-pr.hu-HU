---
title: Fejlesztés Q#-pal és .NET-tel
description: Megtudhatja, hogyan hozhat létre Q#-alkalmazást a .NET-nyelvek használatával.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8733918daa02afaea0fc1994d5f0851d4be9b93
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834329"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="8a4fa-103">Fejlesztés Q#-pal és .NET-tel</span><span class="sxs-lookup"><span data-stu-id="8a4fa-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="8a4fa-104">A Q# úgy lett kifejlesztve, hogy jól együttműködjön a .NET-alapú nyelvekkel, például a C#-pal és az F#-pal.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="8a4fa-105">Ebben az útmutatóban bemutatjuk, hogyan használhatja a Q#-ot egy .NET-nyelven írt gazdaprogrammal.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="8a4fa-106">Először létrehozunk egy Q#-alkalmazást és egy .NET-gazdagépet, majd bemutatjuk, hogyan hívható meg a Q# a gazdagépről.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a4fa-107">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8a4fa-107">Prerequisites</span></span>

- <span data-ttu-id="8a4fa-108">Telepítse a [Q#-projektekhez készült](xref:microsoft.quantum.install.standalone) Quantum Development Kitet.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="8a4fa-109">Q#-kódtár és .NET-gazdagép létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a4fa-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="8a4fa-110">Első lépésként hozzon létre projekteket a Q#-kódtárhoz és a .NET-gazdagéphez, amely Q#-kódtárban definiált műveleteket és függvényeket hívja meg.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="8a4fa-111">Kövesse a fejlesztési környezetéhez tartozó fülön található utasításokat.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="8a4fa-112">Ha a Visual Studiótól vagy a VS Code-tól eltérő szerkesztőt használ, egyszerűen kövesse a parancssor lépéseit.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="8a4fa-113">Visual Studio Code vagy parancssor</span><span class="sxs-lookup"><span data-stu-id="8a4fa-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="8a4fa-114">Új Q#-kódtár létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a4fa-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="8a4fa-115">Hozzon létre egy új, C# vagy F# nyelvű konzolprojektet</span><span class="sxs-lookup"><span data-stu-id="8a4fa-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="8a4fa-116">Adja hozzá referenciaként a Q#-kódtárat a gazdaprogramból</span><span class="sxs-lookup"><span data-stu-id="8a4fa-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="8a4fa-117">[Opcionális] Hozzon létre megoldást mindkét projekthez</span><span class="sxs-lookup"><span data-stu-id="8a4fa-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="8a4fa-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="8a4fa-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="8a4fa-119">Új Q#-kódtár létrehozása</span><span class="sxs-lookup"><span data-stu-id="8a4fa-119">Create a new Q# library</span></span>
  - <span data-ttu-id="8a4fa-120">Lépjen a **Fájl** -> **Új** -> **Projekt** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="8a4fa-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="8a4fa-121">A keresőmezőbe írja be a következőt: Q#</span><span class="sxs-lookup"><span data-stu-id="8a4fa-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="8a4fa-122">Válassza a **Q# Library (Q#-kódtár) lehetőséget**</span><span class="sxs-lookup"><span data-stu-id="8a4fa-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="8a4fa-123">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-123">Select **Next**</span></span>
  - <span data-ttu-id="8a4fa-124">Adja meg a kódtár nevét és helyét</span><span class="sxs-lookup"><span data-stu-id="8a4fa-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="8a4fa-125">Győződjön meg arról, hogy a Place project and solution in same directory (Projekt és megoldás azonos kódtárba helyezése) beállítás **nincs bejelölve**</span><span class="sxs-lookup"><span data-stu-id="8a4fa-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="8a4fa-126">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-126">Select **Create**</span></span>
- <span data-ttu-id="8a4fa-127">Hozzon létre egy új, C# vagy F# nyelvű gazdaprogramot</span><span class="sxs-lookup"><span data-stu-id="8a4fa-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="8a4fa-128">Lépjen a **File (Fájl)** → **New (Új)** → **Project (Projekt)** lehetőséghez</span><span class="sxs-lookup"><span data-stu-id="8a4fa-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="8a4fa-129">Válassza a Console App (.NET Core) Konzolalkalmazás (.NET Core) lehetőséget a C# vagy az F# esetében</span><span class="sxs-lookup"><span data-stu-id="8a4fa-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="8a4fa-130">Kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-130">Select **Next**</span></span>
  - <span data-ttu-id="8a4fa-131">A *megoldás* alatt válassza az Add to solution (Hozzáadás a megoldáshoz) lehetőséget</span><span class="sxs-lookup"><span data-stu-id="8a4fa-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="8a4fa-132">Válasszon egy nevet a gazdaprogram számára</span><span class="sxs-lookup"><span data-stu-id="8a4fa-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="8a4fa-133">Kattintson a **Létrehozás** elemre.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-133">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="8a4fa-134">A Q# meghívása a .NET-ből</span><span class="sxs-lookup"><span data-stu-id="8a4fa-134">Calling into Q# from .NET</span></span>

<span data-ttu-id="8a4fa-135">Miután a fenti utasítások szerint beállította a projekteket, a .NET-konzolalkalmazásból meghívhatja a Q#-ot.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-135">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="8a4fa-136">A Q#-fordító minden Q#-művelethez és -függvényhez .NET-osztályokat hoz létre, amelyek lehetővé teszik, hogy kvantumprogramokat futtathasson egy szimulátoron.</span><span class="sxs-lookup"><span data-stu-id="8a4fa-136">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="8a4fa-137">A [.NET-együttműködési minta](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) például a következő Q#-műveletet tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="8a4fa-137">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="8a4fa-138">Ha ezt a műveletet .NET-ből szeretné meghívni egy kvantumszimulátoron, használhatja a Q#-fordító által létrehozott `RunAlgorithm` .NET-osztály `Run` metódusát:</span><span class="sxs-lookup"><span data-stu-id="8a4fa-138">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="8a4fa-139">C#</span><span class="sxs-lookup"><span data-stu-id="8a4fa-139">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="8a4fa-140">F#</span><span class="sxs-lookup"><span data-stu-id="8a4fa-140">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="8a4fa-141">További lépések</span><span class="sxs-lookup"><span data-stu-id="8a4fa-141">Next steps</span></span>

<span data-ttu-id="8a4fa-142">Most, hogy a Quantum Development Kit a Q#-alkalmazásokhoz, valamint a .NET-tel való együttműködéshez is be van állítva, megírhatja és futtathatja [az első kvantumprogramját](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="8a4fa-142">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
