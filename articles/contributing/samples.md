---
title: Példák a Microsoft QDK
description: Ismerje meg, Hogyan járulhat hozzá a mintakód a Microsoft Quantum Development Kithoz (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024151"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="44344-103">Közreműködő minták a Quantum Development Kit-hez</span><span class="sxs-lookup"><span data-stu-id="44344-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="44344-104">Ha szeretne hozzájárulni a [minták tárházhoz](https://github.com/Microsoft/Quantum)való hozzájáruláshoz, Köszönjük, hogy a kvantum-fejlesztési Közösségnek jobb helyet kíván bevezetni!</span><span class="sxs-lookup"><span data-stu-id="44344-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="44344-105">A Quantum Development Kit Samples repository</span><span class="sxs-lookup"><span data-stu-id="44344-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="44344-106">Annak érdekében, hogy a lehető legnagyobb mértékben segítse elő a hozzájárulását, hasznos lehet gyors áttekintést készíteni a minták tárházának meghatározásáról:</span><span class="sxs-lookup"><span data-stu-id="44344-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

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

<span data-ttu-id="44344-107">Ez azt eredményezi, hogy a [Microsoft/Quantum adattárban](https://github.com/microsoft/Quantum) lévő mintákat különböző mappákba (például `algorithms/`, `arithmetic/`vagy `characterization/`) bontja a tárgyi terület.</span><span class="sxs-lookup"><span data-stu-id="44344-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="44344-108">Az egyes területekhez tartozó mappában minden minta egy olyan mappából áll, amely összegyűjti a felhasználó által a minta megismeréséhez és használatához szükséges összes adatot.</span><span class="sxs-lookup"><span data-stu-id="44344-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="44344-109">A minták strukturálva</span><span class="sxs-lookup"><span data-stu-id="44344-109">How Samples are Structured</span></span>

<span data-ttu-id="44344-110">Tekintse át az egyes mappákat alkotó fájlokat, tekintsük át a [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) mintát.</span><span class="sxs-lookup"><span data-stu-id="44344-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="44344-111">Fájl</span><span class="sxs-lookup"><span data-stu-id="44344-111">File</span></span>              | <span data-ttu-id="44344-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="44344-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="44344-113">Q # projekt a minta létrehozásához a .NET Core SDK használatával</span><span class="sxs-lookup"><span data-stu-id="44344-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="44344-114">Q # műveletek és függvények a mintához</span><span class="sxs-lookup"><span data-stu-id="44344-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="44344-115">C#a minta futtatásához használt gazda program</span><span class="sxs-lookup"><span data-stu-id="44344-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="44344-116">A minta futtatásához használt Python-gazda program</span><span class="sxs-lookup"><span data-stu-id="44344-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="44344-117">Dokumentáció a minta működéséről és használatáról</span><span class="sxs-lookup"><span data-stu-id="44344-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="44344-118">Nem minden mintának ugyanazokat a fájlokat fogja tartalmazni (például: néhány minta csak akkor lehet C#, ha mások nem rendelkeznek Python-gazdagépgel, vagy bizonyos minták segédszolgáltatása-adatfájlokat is igényelhetnek).</span><span class="sxs-lookup"><span data-stu-id="44344-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="44344-119">Hasznos információs fájl anatómiája</span><span class="sxs-lookup"><span data-stu-id="44344-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="44344-120">Az egyik különösen fontos fájl, bár a `README.md` fájl, mivel a felhasználóknak a példával kell megkezdeniük.</span><span class="sxs-lookup"><span data-stu-id="44344-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="44344-121">Minden `README.md`nak olyan metaadatokkal kell kezdődnie, amely segít a docs.microsoft.com/samples a hozzájárulás megtalálásában.</span><span class="sxs-lookup"><span data-stu-id="44344-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="44344-122">Nézze meg, hogyan jelenik meg a chsh-játék mintája</span><span class="sxs-lookup"><span data-stu-id="44344-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="44344-123">Ez a metaadatok olyan YAML- [fejlécként](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) vannak megadva, amely megadja, hogy a minta Milyen nyelveket mutat be (ez általában `qsharp`, `csharp`és `python`), és hogy a minta mely termékekre vonatkozik (jellemzően csak `qdk`).</span><span class="sxs-lookup"><span data-stu-id="44344-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="44344-124">Ahhoz, hogy a minta megjelenjen a docs.microsoft.com/samples, a fejlécben szereplő `page_type: sample` kulcs szükséges.</span><span class="sxs-lookup"><span data-stu-id="44344-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="44344-125">Hasonlóképpen, a `product` és `language` kulcsok kritikus fontosságúak ahhoz, hogy a felhasználók megtalálják és futtassák a mintát.</span><span class="sxs-lookup"><span data-stu-id="44344-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="44344-126">Ezt követően hasznos lehet egy rövid bevezetőt adni, amely megadja, hogy mit tesz az új minta:</span><span class="sxs-lookup"><span data-stu-id="44344-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="44344-127">A minta felhasználói azt is értékelik, hogy mire van szükségük a futtatásához (pl.: a felhasználók csak a Quantum Development Kit-t használják, vagy további szoftverekre van szükségük, mint például a Node. js?):</span><span class="sxs-lookup"><span data-stu-id="44344-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="44344-128">A következő módon megadhatja, hogy a felhasználók hogyan futtathatják a mintát:</span><span class="sxs-lookup"><span data-stu-id="44344-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="44344-129">Végezetül pedig hasznos lehet tájékoztatni a felhasználókat arról, hogy a mintában szereplő összes fájl milyen további információkat tartalmaz:</span><span class="sxs-lookup"><span data-stu-id="44344-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="44344-130">Ügyeljen arra, hogy itt abszolút URL-címeket használjon, mivel a minta egy másik URL-címen fog megjelenni, amikor a docs.microsoft.com/samples-on jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="44344-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>