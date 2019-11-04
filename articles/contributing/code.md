---
title: Közreműködő kód | Microsoft Docs
description: Közreműködő kód
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: cca50e6c63d4bb982aa5f0a59fc19d08ecbec508
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185902"
---
# <a name="contributing-code"></a><span data-ttu-id="3bd77-103">Közreműködő kód</span><span class="sxs-lookup"><span data-stu-id="3bd77-103">Contributing Code</span></span> #

<span data-ttu-id="3bd77-104">A hibák jelentése és a dokumentáció fejlesztése mellett a kód a Quantum Development Kit-hez való hozzájárulása is nagyon közvetlen módja lehet a vállalatoknak a kvantum-programozási Közösségben.</span><span class="sxs-lookup"><span data-stu-id="3bd77-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="3bd77-105">A kód hozzájárulásával segíthet a problémák megoldásában, új példák megadásában, a meglévő kódtárak használatának megkönnyítésében, vagy akár teljesen új funkciók hozzáadásában is.</span><span class="sxs-lookup"><span data-stu-id="3bd77-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="3bd77-106">Ebben az útmutatóban részletesen ismertetjük, hogy mi a teendő, ha áttekintjük a lekéréses kérelmeket, hogy a lehető legjobb segítséget nyújtson.</span><span class="sxs-lookup"><span data-stu-id="3bd77-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="3bd77-107">Mit keresünk</span><span class="sxs-lookup"><span data-stu-id="3bd77-107">What We Look For</span></span> ##

<span data-ttu-id="3bd77-108">Az ideális kód hozzájárulása a Quantum Development Kit-adattár meglévő munkája alapján javítja ki a problémákat, kibővítheti a meglévő funkciókat, vagy hozzáadhat új szolgáltatásokat, amelyek egy adattár hatókörén belül találhatók.</span><span class="sxs-lookup"><span data-stu-id="3bd77-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="3bd77-109">Ha elfogadjuk a kód bevonását, az a Quantum Development Kit részévé válik, így az új funkciók ugyanúgy lesznek felszabadítva, karbantartva és kifejlesztve, mint a Quantum Development Kit többi része.</span><span class="sxs-lookup"><span data-stu-id="3bd77-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="3bd77-110">Így hasznos lehet, ha a hozzájárulás által hozzáadott funkciók jól teszteltek és dokumentálva vannak.</span><span class="sxs-lookup"><span data-stu-id="3bd77-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="3bd77-111">Egység tesztek</span><span class="sxs-lookup"><span data-stu-id="3bd77-111">Unit Tests</span></span> ###

<span data-ttu-id="3bd77-112">A Q # functions, Operations és felhasználó által definiált típusokat, amelyek a tárakat (például a canonot) a fejlesztés részeként automatikusan tesztelik a [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) adattárban.</span><span class="sxs-lookup"><span data-stu-id="3bd77-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="3bd77-113">Új lekéréses kérelem megnyitásakor – például az Azure- [folyamatok](https://azure.microsoft.com/services/devops/pipelines/) konfigurációjában – a lekéréses kérelem módosításai nem bontják le azokat a meglévő funkciókat, amelyekre a Quantum programozási Közösség függ.</span><span class="sxs-lookup"><span data-stu-id="3bd77-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>
<span data-ttu-id="3bd77-114">Ezek a tesztek a [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) csomag használatával íródnak, amely a Q # függvényeket és műveleteket teszteli a [xUnit](https://xunit.github.io/) -keretrendszer számára.</span><span class="sxs-lookup"><span data-stu-id="3bd77-114">These tests are written using the [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package, which exposes Q# functions and operations as tests for the [xUnit](https://xunit.github.io/) framework.</span></span>

<span data-ttu-id="3bd77-115">A [`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) ezt a xUnit-integrációt használja a `Test`-ban végződő függvények vagy műveletek futtatásához.</span><span class="sxs-lookup"><span data-stu-id="3bd77-115">The [`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) uses this xUnit integration to run any functions or operations ending in `Test`.</span></span>
<span data-ttu-id="3bd77-116">A következő függvény például annak biztosítására szolgál, hogy a <xref:microsoft.quantum.canon.fst> és a <xref:microsoft.quantum.canon.snd> függvény a megfelelő kimeneteket adja vissza egy reprezentatív példában.</span><span class="sxs-lookup"><span data-stu-id="3bd77-116">For instance, the following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="3bd77-117">Ha a `Fst` vagy `Snd` kimenete helytelen, a rendszer a `fail` utasítást használja, hogy a teszt sikertelen legyen.</span><span class="sxs-lookup"><span data-stu-id="3bd77-117">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="3bd77-118">Összetettebb feltételek ellenőrizhetők a szabványos könyvtárak útmutatójának [tesztelés szakaszában](xref:microsoft.quantum.libraries.diagnostics) található módszerek használatával.</span><span class="sxs-lookup"><span data-stu-id="3bd77-118">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="3bd77-119">A következő teszt például azt ellenőrzi, hogy a `H(q); X(q); H(q);`, ahogyan az <xref:microsoft.quantum.canon.applywith> meghívja a `Z(q)`.</span><span class="sxs-lookup"><span data-stu-id="3bd77-119">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```qsharp
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="3bd77-120">Új funkciók hozzáadásakor érdemes új teszteket is felvenni, hogy az Ön hozzájárulása valóban a kívánt módon legyen.</span><span class="sxs-lookup"><span data-stu-id="3bd77-120">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="3bd77-121">Ez segíti a Közösség többi részét a funkció fenntartásában és fejlesztésében, és különösen segít más fejlesztőknek, hogy a szolgáltatásra támaszkodni tudjanak.</span><span class="sxs-lookup"><span data-stu-id="3bd77-121">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="3bd77-122">Ez fordítva is működik.</span><span class="sxs-lookup"><span data-stu-id="3bd77-122">This works the other way around, too!</span></span>
> <span data-ttu-id="3bd77-123">Ha van olyan meglévő szolgáltatás, amely néhány tesztet tartalmaz, akkor a tesztelési lefedettség hozzáadásával nagy mértékben járulhat hozzá a Közösséghez.</span><span class="sxs-lookup"><span data-stu-id="3bd77-123">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="3bd77-124">A helyszíni tesztek a Visual Studio test Explorer vagy a `dotnet test` paranccsal is futtathatók, így a lekéréses kérelem megnyitása előtt ellenőrizheti a hozzájárulását.</span><span class="sxs-lookup"><span data-stu-id="3bd77-124">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="3bd77-125">Ha elutasítja a lekéréses kérelmet</span><span class="sxs-lookup"><span data-stu-id="3bd77-125">When We'll Reject a Pull Request</span></span> ##

<span data-ttu-id="3bd77-126">Időnként elutasítja a hozzájárulás lekérését.</span><span class="sxs-lookup"><span data-stu-id="3bd77-126">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="3bd77-127">Ha ez történik, ez nem jelenti azt, hogy rossz, mert számos oka lehet annak, hogy nem tudjuk elfogadni az adott hozzájárulást.</span><span class="sxs-lookup"><span data-stu-id="3bd77-127">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="3bd77-128">Talán a legtöbb esetben a kvantum-programozási Közösséghez való hozzájárulás egy nagyon jó, de a Quantum Development Kit-Tárházak nem a megfelelő hely a fejlesztéshez.</span><span class="sxs-lookup"><span data-stu-id="3bd77-128">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="3bd77-129">Ilyen esetekben arra törekszünk, hogy saját tárházat---a Quantum Development Kit erősségének részeként, hogy könnyen elvégezhető és terjeszthető legyen a saját könyvtárai a GitHub és a NuGet.org használatával, ugyanúgy, ahogy a Canon és a kémia is kiterjeszthető. tárak ma.</span><span class="sxs-lookup"><span data-stu-id="3bd77-129">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="3bd77-130">Máskor elutasítottuk a jó hozzájárulást, mivel még nem áll készen a karbantartásra és a fejlesztésre.</span><span class="sxs-lookup"><span data-stu-id="3bd77-130">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="3bd77-131">Nehéz lehet mindent megtenni, ezért tervezzük meg, hogy milyen funkciókra van lehetőségünk a legjobb megoldásként.</span><span class="sxs-lookup"><span data-stu-id="3bd77-131">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="3bd77-132">Ez lehet egy másik eset, amikor egy funkciót külső gyártótól származó könyvtárként szabadít fel.</span><span class="sxs-lookup"><span data-stu-id="3bd77-132">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="3bd77-133">Azt is megteheti, hogy segít a szolgáltatás módosításában, hogy jobban illeszkedjen az ütemtervhez, hogy a lehető legjobb munkát végezzük.</span><span class="sxs-lookup"><span data-stu-id="3bd77-133">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="3bd77-134">A lekéréses kérelem módosításait is kérik, ha több dokumentációra vagy egységre vonatkozó tesztre van szükség, amely segít a használatában, vagy ha a Q # könyvtáraiban lévő többitől függően nem elég, hogy a felhasználók megtalálják a funkciót.</span><span class="sxs-lookup"><span data-stu-id="3bd77-134">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="3bd77-135">Ezekben az esetekben megpróbálunk néhány tanácsot készíteni a kód felülvizsgálatáról arról, hogy milyen felvehetők vagy módosíthatók, hogy a hozzájárulása könnyebb legyen a számunkra.</span><span class="sxs-lookup"><span data-stu-id="3bd77-135">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="3bd77-136">Végül a [Microsoft nyílt forráskódjának viselkedési szabályzatában](https://opensource.microsoft.com/codeofconduct/)ismertetett módon nem fogadhatunk olyan hozzájárulásokat, amelyek kárt okoznak a kvantum-számítástechnikai Közösség számára.</span><span class="sxs-lookup"><span data-stu-id="3bd77-136">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="3bd77-137">Szeretnénk biztosítani, hogy a hozzájárulások a teljes kvantum-számítástechnikai Közösséget, a jelenlegi csodálatos sokféleségben és a jövőben is kiszolgálják, ahogy az egyre nagyobb mértékben növekszik.</span><span class="sxs-lookup"><span data-stu-id="3bd77-137">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="3bd77-138">Nagyra értékeljük segítségét ennek a célnak a megvalósításában.</span><span class="sxs-lookup"><span data-stu-id="3bd77-138">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3bd77-139">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="3bd77-139">Next steps</span></span> ##

<span data-ttu-id="3bd77-140">Köszönjük, hogy a Quantum Development Kit nagyszerű erőforrást biztosít a teljes kvantum-programozási Közösség számára!</span><span class="sxs-lookup"><span data-stu-id="3bd77-140">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="3bd77-141">További információért folytassa a következő útmutatóval a Q # Style-on.</span><span class="sxs-lookup"><span data-stu-id="3bd77-141">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3bd77-142">A Q # Style irányelvek ismertetése</span><span class="sxs-lookup"><span data-stu-id="3bd77-142">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)
