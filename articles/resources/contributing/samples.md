---
title: Példák a Microsoft QDK
description: Ismerje meg, Hogyan járulhat hozzá a mintakód a Microsoft Quantum Development Kithoz (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0c940a4cf228c694a899988f469158b1bb6e2425
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847582"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="35535-103">Közreműködő minták a Quantum Development Kit-hez</span><span class="sxs-lookup"><span data-stu-id="35535-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="35535-104">Ha szeretne hozzájárulni a [minták tárházhoz](https://github.com/Microsoft/Quantum)való hozzájáruláshoz, Köszönjük, hogy a kvantum-fejlesztési Közösségnek jobb helyet kíván bevezetni!</span><span class="sxs-lookup"><span data-stu-id="35535-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="35535-105">A Quantum Development Kit Samples repository</span><span class="sxs-lookup"><span data-stu-id="35535-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="35535-106">Annak érdekében, hogy a lehető legnagyobb mértékben segítse elő a hozzájárulását, hasznos lehet gyors áttekintést készíteni a minták tárházának meghatározásáról:</span><span class="sxs-lookup"><span data-stu-id="35535-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="35535-107">Ez azt eredményezi, hogy a [Microsoft/Quantum adattárban](https://github.com/microsoft/Quantum) lévő mintákat különböző mappákba (például `algorithms/` ,, `arithmetic/` vagy) bontottuk `characterization/` .</span><span class="sxs-lookup"><span data-stu-id="35535-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="35535-108">Az egyes területekhez tartozó mappában minden minta egy olyan mappából áll, amely összegyűjti a felhasználó által a minta megismeréséhez és használatához szükséges összes adatot.</span><span class="sxs-lookup"><span data-stu-id="35535-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="35535-109">A minták strukturálva</span><span class="sxs-lookup"><span data-stu-id="35535-109">How Samples are Structured</span></span>

<span data-ttu-id="35535-110">Tekintse át az egyes mappákat alkotó fájlokat, tekintsük át a [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) mintát.</span><span class="sxs-lookup"><span data-stu-id="35535-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="35535-111">Fájl</span><span class="sxs-lookup"><span data-stu-id="35535-111">File</span></span>              | <span data-ttu-id="35535-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="35535-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="35535-113">Q# a minta létrehozásához használt projekt .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="35535-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="35535-114">Q# a mintához tartozó műveletek és függvények</span><span class="sxs-lookup"><span data-stu-id="35535-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="35535-115">A minta futtatására szolgáló C#-gazda program</span><span class="sxs-lookup"><span data-stu-id="35535-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="35535-116">A minta futtatásához használt Python-gazda program</span><span class="sxs-lookup"><span data-stu-id="35535-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="35535-117">Dokumentáció a minta működéséről és használatáról</span><span class="sxs-lookup"><span data-stu-id="35535-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="35535-118">Nem minden mintának ugyanazokat a fájlokat fogja tartalmazni (például: néhány minta csak C# lehet, másoknak nem lehet Python-gazdagépe, vagy bizonyos példákban segédszolgáltatása adatfájlok is működhetnek).</span><span class="sxs-lookup"><span data-stu-id="35535-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="35535-119">Hasznos információs fájl anatómiája</span><span class="sxs-lookup"><span data-stu-id="35535-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="35535-120">Az egyik különösen fontos fájl, azonban a `README.md` fájl, ahogy a felhasználóknak meg kell kezdeniük a mintát!</span><span class="sxs-lookup"><span data-stu-id="35535-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="35535-121">Mindegyiknek olyan `README.md` metaadatokkal kell kezdődnie, amelyek segítenek a docs.microsoft.com/Samples megtalálásában.</span><span class="sxs-lookup"><span data-stu-id="35535-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="35535-122">Nézze meg, hogyan jelenik meg a chsh-játék mintája</span><span class="sxs-lookup"><span data-stu-id="35535-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="35535-123">Ez a metaadatok olyan YAML- [fejlécként](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) jelennek meg, amely megadja, hogy a minta milyen nyelvekre terjed ki (ez általában a, a `qsharp` `csharp` és a `python` ), valamint hogy a minta mely termékekre vonatkozik (jellemzően, csak `qdk` ).</span><span class="sxs-lookup"><span data-stu-id="35535-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="35535-124">Ahhoz, `page_type: sample` hogy a minta megjelenjen a docs.microsoft.com/Samples, a fejlécben szereplő kulcs megadása kötelező.</span><span class="sxs-lookup"><span data-stu-id="35535-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="35535-125">Hasonlóképpen a `product` és a `language` kulcsok kritikus fontosságúak ahhoz, hogy segítséget nyújtson a felhasználóknak a minta megtalálásában és futtatásában.</span><span class="sxs-lookup"><span data-stu-id="35535-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="35535-126">Ezt követően hasznos lehet egy rövid bevezetőt adni, amely megadja, hogy mit tesz az új minta:</span><span class="sxs-lookup"><span data-stu-id="35535-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="35535-127">A minta felhasználói azt is értékelik, hogy mire van szükségük a futtatásához (például: a felhasználók csak saját maga szeretnék kiépíteni a kvantum-fejlesztési csomagot, vagy további szoftverekre van szükségük, például node.js?):</span><span class="sxs-lookup"><span data-stu-id="35535-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="35535-128">A következő módon megadhatja, hogy a felhasználók hogyan futtathatják a mintát:</span><span class="sxs-lookup"><span data-stu-id="35535-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="35535-129">Végezetül pedig hasznos lehet tájékoztatni a felhasználókat arról, hogy a mintában szereplő összes fájl milyen további információkat tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="35535-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="35535-130">Ügyeljen arra, hogy itt abszolút URL-címeket használjon, mivel a minta egy másik URL-címen fog megjelenni, amikor a docs.microsoft.com/samples-on jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="35535-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
