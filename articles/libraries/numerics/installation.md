---
title: Numerikus könyvtárak telepítése és érvényesítése | Microsoft Docs
description: Numerikus könyvtárak telepítése és érvényesítése
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184627"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="ada57-103">Numerikus könyvtárak telepítése és érvényesítése</span><span class="sxs-lookup"><span data-stu-id="ada57-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="ada57-104">A Quantum Development Kit a [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet-csomagon keresztül biztosítja a numerikus funkciók használatát.</span><span class="sxs-lookup"><span data-stu-id="ada57-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="ada57-105">**Visual Studio > = 2019:** Ha a Visual Studio 2019-es vagy újabb verzióját használja, a numerikus csomagokat a NuGet csomagkezelő használatával adhatja hozzá.</span><span class="sxs-lookup"><span data-stu-id="ada57-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="ada57-106">Ehhez válassza a "NuGet-csomagok kezelése..." lehetőséget. a Visual Studióban a "projekt" menüpontban.</span><span class="sxs-lookup"><span data-stu-id="ada57-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="ada57-107">A Tallózás lapon keresse meg a "Microsoft. Quantum. numerikus" nevű csomagot.</span><span class="sxs-lookup"><span data-stu-id="ada57-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="ada57-108">Győződjön meg arról, hogy az "előzetes kiadás belefoglalása" jelölőnégyzet be van jelölve</span><span class="sxs-lookup"><span data-stu-id="ada57-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="ada57-109">Ekkor megjelenik a letölthető csomagok listája.</span><span class="sxs-lookup"><span data-stu-id="ada57-109">This will list the packages available for download.</span></span>
<span data-ttu-id="ada57-110">A "Microsoft. Quantum. Numbers" kifejezés fölé helyezve egy lefelé mutató nyíl látható a verziószámtól jobbra.</span><span class="sxs-lookup"><span data-stu-id="ada57-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="ada57-111">Kattintson a nyílra a numerikus csomagok telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ada57-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="ada57-112">További részletekért tekintse meg a [Package Manager felhasználói felületi útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span><span class="sxs-lookup"><span data-stu-id="ada57-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="ada57-113">Azt is megteheti, hogy a Package Manager konzol segítségével hozzáadja a numerikus függvénytárat a projekthez a parancssori felületen keresztül.</span><span class="sxs-lookup"><span data-stu-id="ada57-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="ada57-114">A Package Manager konzolon futtassa a következőt:</span><span class="sxs-lookup"><span data-stu-id="ada57-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="ada57-115">További részletekért tekintse meg a [Package Manager konzol útmutatóját](https://docs.microsoft.com/nuget/tools/package-manager-console).</span><span class="sxs-lookup"><span data-stu-id="ada57-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="ada57-116">**Parancssor vagy Visual Studio code:** Ha a parancssort saját vagy a Visual Studio Code-ból szeretné használni, a `dotnet` paranccsal adhat hozzá NuGet-csomagot a projekthez:</span><span class="sxs-lookup"><span data-stu-id="ada57-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="ada57-117">A telepítés ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="ada57-117">Verifying your installation</span></span>

<span data-ttu-id="ada57-118">A Quantum Development Kit többi részéhez hasonlóan a numerikus könyvtár olyan mintákat tartalmaz, amelyek segítségével a lehető leggyorsabban kezdheti meg a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="ada57-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="ada57-119">Ha tesztelni szeretné a telepítést ezeken a mintákon, akkor a [fő minták tárházát](https://github.com/Microsoft/Quantum) , majd futtassa az egyik mintát.</span><span class="sxs-lookup"><span data-stu-id="ada57-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="ada57-120">A [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) minta futtatása:</span><span class="sxs-lookup"><span data-stu-id="ada57-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```