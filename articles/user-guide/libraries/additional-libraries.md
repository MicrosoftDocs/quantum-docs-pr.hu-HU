---
title: További Q# kódtárak használata
description: Ismerje meg, hogyan adhat hozzá további Q# kódtárakat a kvantum-alkalmazásokhoz.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992139"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="71e26-103">További Q# kódtárak használata</span><span class="sxs-lookup"><span data-stu-id="71e26-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="71e26-104">A Quantum Development Kit további, tartományra jellemző funkciókat biztosít a projektekhez adható _NuGet-csomagokon_ keresztül Q# .</span><span class="sxs-lookup"><span data-stu-id="71e26-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="71e26-105">Q# Erőforrástár</span><span class="sxs-lookup"><span data-stu-id="71e26-105">Q# Library</span></span>  | <span data-ttu-id="71e26-106">NuGet-csomag</span><span class="sxs-lookup"><span data-stu-id="71e26-106">NuGet package</span></span> | <span data-ttu-id="71e26-107">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="71e26-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="71e26-108">Q# Standard könyvtár</span><span class="sxs-lookup"><span data-stu-id="71e26-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="71e26-109">**Microsoft. Quantum. Standard**</span><span class="sxs-lookup"><span data-stu-id="71e26-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="71e26-110">Alapértelmezés szerint tartalmazza</span><span class="sxs-lookup"><span data-stu-id="71e26-110">Included by default</span></span> |
| [<span data-ttu-id="71e26-111">Kvantumkémiai kódtár</span><span class="sxs-lookup"><span data-stu-id="71e26-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="71e26-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="71e26-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="71e26-113">Kvantumnumerikus kódtár</span><span class="sxs-lookup"><span data-stu-id="71e26-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="71e26-114">**Microsoft. Quantum. numerikus számok**</span><span class="sxs-lookup"><span data-stu-id="71e26-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="71e26-115">Kvantum gépi tanulási kódtár</span><span class="sxs-lookup"><span data-stu-id="71e26-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="71e26-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="71e26-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="71e26-117">Miután telepítette a Quantum Development Kit-t az előnyben részesített környezettel és a gazdagép nyelvével való használatra, a további telepítés nélkül könnyedén hozzáadhat könyvtárakat az egyes Q# projektekhez.</span><span class="sxs-lookup"><span data-stu-id="71e26-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="71e26-118">Egyes Q# könyvtárak jól használhatók olyan további eszközökkel, amelyek a programok mellett működnek Q# , vagy amelyek integrálva vannak a gazdagép alkalmazásaival.</span><span class="sxs-lookup"><span data-stu-id="71e26-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="71e26-119">A [kémia könyvtár telepítési útmutatója](xref:microsoft.quantum.chemistry.concepts.installation) például leírja, hogyan használhatja a [ **Microsoft. Quantum. kémia** csomagot](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) a NWChem számítási kémia platformmal, és hogyan telepítheti a `qdk-chem` parancssori eszközöket a kvantum-kémiai adatmennyiségek használatához.</span><span class="sxs-lookup"><span data-stu-id="71e26-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-applications-or-net-interopability"></a>[<span data-ttu-id="71e26-120">Q# alkalmazások vagy .NET-együttműködés</span><span class="sxs-lookup"><span data-stu-id="71e26-120">Q# applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="71e26-121">**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal hozzáadhat egy NuGet-csomagot a projekthez.</span><span class="sxs-lookup"><span data-stu-id="71e26-121">**Command prompt or Visual Studio Code:** Using the command prompt on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="71e26-122">A [**Microsoft. Quantum. numerikus**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) csomagok hozzáadásához például futtassa a következő parancsot:</span><span class="sxs-lookup"><span data-stu-id="71e26-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="71e26-123">**Visual Studio:** Ha a Visual Studio 2019-es vagy újabb verzióját használja, további csomagokat adhat hozzá Q# a NuGet csomagkezelő használatával.</span><span class="sxs-lookup"><span data-stu-id="71e26-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="71e26-124">Csomag betöltése:</span><span class="sxs-lookup"><span data-stu-id="71e26-124">To load a package:</span></span> 
1. <span data-ttu-id="71e26-125">A Visual Studióban megnyitott projekttel válassza a **NuGet-csomagok kezelése...** lehetőséget a **projekt** menüben.</span><span class="sxs-lookup"><span data-stu-id="71e26-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="71e26-126">Kattintson a **Tallózás**elemre, válassza az **előzetes kiadás belefoglalása** lehetőséget, és keresse meg a "Microsoft. Quantum. numerikus" nevű csomagot.</span><span class="sxs-lookup"><span data-stu-id="71e26-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="71e26-127">Ekkor megjelenik a letölthető csomagok listája.</span><span class="sxs-lookup"><span data-stu-id="71e26-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="71e26-128">Vigye a kurzort a **Microsoft. Quantum.** Numbers elemre, majd kattintson a verziószám jobb oldalán lévő lefelé mutató nyílra a numerikus csomagok telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="71e26-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="71e26-129">További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="71e26-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="71e26-130">Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a numerikus függvénytárat a projekthez a parancssori felületen keresztül.</span><span class="sxs-lookup"><span data-stu-id="71e26-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![A Package Manager konzol használata a parancssorból](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="71e26-132">A Package Manager konzolon futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="71e26-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="71e26-133">További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="71e26-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="71e26-134">Q#Jegyzetfüzetek</span><span class="sxs-lookup"><span data-stu-id="71e26-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="71e26-135">Q#A [ `%package` Magic parancs](xref:microsoft.quantum.iqsharp.magic-ref.package)használatával további csomagokat is használhat az I jegyzetfüzetben.</span><span class="sxs-lookup"><span data-stu-id="71e26-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="71e26-136">Ha például a [**Microsoft. Quantum. numerikus**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) csomagokat szeretné felvenni egy I jegyzetfüzetben való használatra Q# , futtassa a következő parancsot egy jegyzetfüzet-cellában:</span><span class="sxs-lookup"><span data-stu-id="71e26-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="71e26-137">Ezt a parancsot követve a csomag a jegyzetfüzetben lévő összes cella számára elérhető.</span><span class="sxs-lookup"><span data-stu-id="71e26-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="71e26-138">Ahhoz, hogy a csomag elérhető legyen a Q# jelenlegi munkaterületen található kódból, a csomag hozzáadása után töltse be újra a munkaterületet:</span><span class="sxs-lookup"><span data-stu-id="71e26-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="71e26-139">Python-együttműködés</span><span class="sxs-lookup"><span data-stu-id="71e26-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="71e26-140">A metódus használatával további csomagokat is használhat egy Python-gazda programban [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) .</span><span class="sxs-lookup"><span data-stu-id="71e26-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="71e26-141">Ha például a [**Microsoft. Quantum. numerikus**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) csomagokat szeretné felvenni egy I jegyzetfüzetben való használatra Q# , futtassa a következő Python-kódot:</span><span class="sxs-lookup"><span data-stu-id="71e26-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="71e26-142">A parancs követése után a csomag elérhetővé válik bármely, a Q# használatával lefordított kód számára `qsharp.compile` .</span><span class="sxs-lookup"><span data-stu-id="71e26-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="71e26-143">Ahhoz, hogy a csomag elérhető legyen a Q# jelenlegi munkaterületen található kódból, a csomag hozzáadása után töltse be újra a munkaterületet:</span><span class="sxs-lookup"><span data-stu-id="71e26-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
