---
title: Microsoft Quantum numerikus könyvtárak – telepítés és érvényesítés
description: Megtudhatja, hogyan adhatja hozzá a Microsoft Quantum numerikus kódtárat a Visual Studio 2019-es vagy újabb verziójának telepítéséhez.
author: thomashaener
ms.author: thhaner
ms.date: 05/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 60ee91a552fad5becf8eda437406b6e0dfba0eb4
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275191"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="3f0c4-103">Numerikus könyvtárak telepítése és érvényesítése</span><span class="sxs-lookup"><span data-stu-id="3f0c4-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="3f0c4-104">A Quantum Development Kit a NuGet-csomagon keresztül biztosítja a numerikus funkciók használatát [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) .</span><span class="sxs-lookup"><span data-stu-id="3f0c4-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="3f0c4-105">**Visual Studio >= 2019:** Ha a Visual Studio 2019-es vagy újabb verzióját használja, a numerikus csomagokat a NuGet csomagkezelő használatával adhatja hozzá.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="3f0c4-106">Ehhez válassza a "NuGet-csomagok kezelése..." lehetőséget. a Visual Studióban a "projekt" menüpontban.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="3f0c4-107">A Tallózás lapon keresse meg a "Microsoft. Quantum. numerikus" nevű csomagot.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="3f0c4-108">Győződjön meg arról, hogy az "előzetes kiadás belefoglalása" jelölőnégyzet be van jelölve</span><span class="sxs-lookup"><span data-stu-id="3f0c4-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="3f0c4-109">Ekkor megjelenik a letölthető csomagok listája.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-109">This will list the packages available for download.</span></span>
<span data-ttu-id="3f0c4-110">A "Microsoft. Quantum. Numbers" kifejezés fölé helyezve egy lefelé mutató nyíl látható a verziószámtól jobbra.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="3f0c4-111">Kattintson a nyílra a numerikus csomagok telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="3f0c4-112">További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="3f0c4-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="3f0c4-113">Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a numerikus függvénytárat a projekthez a parancssori felületen keresztül.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![A Package Manager konzol használata a parancssorból](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="3f0c4-115">A Package Manager konzolon futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="3f0c4-115">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="3f0c4-116">További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="3f0c4-116">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="3f0c4-117">**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal adhat hozzá NuGet-csomagot a projekthez:</span><span class="sxs-lookup"><span data-stu-id="3f0c4-117">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="3f0c4-118">A telepítés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="3f0c4-118">Verifying your installation</span></span>

<span data-ttu-id="3f0c4-119">A Quantum Development Kit többi részéhez hasonlóan a numerikus könyvtár olyan mintákat tartalmaz, amelyek segítségével a lehető leggyorsabban kezdheti meg a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-119">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="3f0c4-120">Ha tesztelni szeretné a telepítést ezeken a mintákon, akkor a [fő minták tárházát](https://github.com/Microsoft/Quantum) , majd futtassa az egyik mintát.</span><span class="sxs-lookup"><span data-stu-id="3f0c4-120">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="3f0c4-121">A minta futtatása [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) :</span><span class="sxs-lookup"><span data-stu-id="3f0c4-121">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/samples/numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics/CustomModAdd
dotnet run
```
