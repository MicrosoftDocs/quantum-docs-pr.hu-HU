---
title: A Microsoft QDK való hozzájárulás kódja
description: Megtudhatja, Hogyan járulhat hozzá a minta-és a függvénytár-kódokhoz a Microsoft Quantum Development Kithoz (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: b27d084bbe2cda878efa6250c52c0ae628637850
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834890"
---
# <a name="contributing-code"></a><span data-ttu-id="78913-103">Hozzájárulás a kódhoz</span><span class="sxs-lookup"><span data-stu-id="78913-103">Contributing Code</span></span>

<span data-ttu-id="78913-104">A hibák jelentése és a dokumentáció fejlesztése mellett a kód a Quantum Development Kit-hez való hozzájárulása is nagyon közvetlen módja lehet a vállalatoknak a kvantum-programozási Közösségben.</span><span class="sxs-lookup"><span data-stu-id="78913-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="78913-105">A kód hozzájárulásával segíthet a problémák megoldásában, új példák megadásában, a meglévő kódtárak használatának megkönnyítésében, vagy akár teljesen új funkciók hozzáadásában is.</span><span class="sxs-lookup"><span data-stu-id="78913-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="78913-106">Ebben az útmutatóban részletesen ismertetjük, hogy mi a teendő, ha áttekintjük a lekéréses kérelmeket, hogy a lehető legjobb segítséget nyújtson.</span><span class="sxs-lookup"><span data-stu-id="78913-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="78913-107">Mit keresünk</span><span class="sxs-lookup"><span data-stu-id="78913-107">What We Look For</span></span>

<span data-ttu-id="78913-108">Az ideális kód hozzájárulása a Quantum Development Kit-adattár meglévő munkája alapján javítja ki a problémákat, kibővítheti a meglévő funkciókat, vagy hozzáadhat új szolgáltatásokat, amelyek egy adattár hatókörén belül találhatók.</span><span class="sxs-lookup"><span data-stu-id="78913-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="78913-109">Ha elfogadjuk a kód bevonását, az a Quantum Development Kit részévé válik, így az új funkciók ugyanúgy lesznek felszabadítva, karbantartva és kifejlesztve, mint a Quantum Development Kit többi része.</span><span class="sxs-lookup"><span data-stu-id="78913-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="78913-110">Így hasznos lehet, ha a hozzájárulás által hozzáadott funkciók jól teszteltek és dokumentálva vannak.</span><span class="sxs-lookup"><span data-stu-id="78913-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="78913-111">Egység tesztek</span><span class="sxs-lookup"><span data-stu-id="78913-111">Unit Tests</span></span>

<span data-ttu-id="78913-112">A Q# könyvtárakat, például a canont alkotó függvények, műveletek és felhasználó által definiált típusok a [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) adattár fejlesztésének részeként automatikusan tesztelésre kerülnek.</span><span class="sxs-lookup"><span data-stu-id="78913-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="78913-113">Új lekéréses kérelem megnyitásakor – például az Azure- [folyamatok](https://azure.microsoft.com/services/devops/pipelines/) konfigurációjában – a lekéréses kérelem módosításai nem bontják le azokat a meglévő funkciókat, amelyekre a Quantum programozási Közösség függ.</span><span class="sxs-lookup"><span data-stu-id="78913-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="78913-114">A legújabb Q# verzióban az egység-tesztek az attribútummal vannak meghatározva `@Test("QuantumSimulator")` .</span><span class="sxs-lookup"><span data-stu-id="78913-114">With the latest Q# version, unit tests are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="78913-115">Az argumentum lehet "QuantumSimulator", "ToffoliSimulator", "TraceSimulator" vagy bármely teljesen minősített név, amely megadja a Futtatás célját.</span><span class="sxs-lookup"><span data-stu-id="78913-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the run target.</span></span> <span data-ttu-id="78913-116">Több, különböző futtatási célokat meghatározó attribútum is csatlakoztatható ugyanahhoz a meghívóhoz.</span><span class="sxs-lookup"><span data-stu-id="78913-116">Several attributes defining different run targets may be attached to the same callable.</span></span> <span data-ttu-id="78913-117">A tesztek némelyike továbbra is az elavult [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) csomagot használja, amely Q# `Test` a [xUnit](https://xunit.github.io/) -keretrendszerbe végződő összes funkciót és műveletet elérhetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="78913-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="78913-118">Ez a csomag már nem szükséges az egységbeli tesztek definiálásához.</span><span class="sxs-lookup"><span data-stu-id="78913-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="78913-119">A következő függvény használatával biztosítható, hogy a <xref:microsoft.quantum.canon.fst> és a <xref:microsoft.quantum.canon.snd> függvények a megfelelő kimeneteket adják vissza egy reprezentatív példában.</span><span class="sxs-lookup"><span data-stu-id="78913-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="78913-120">Ha a vagy a kimenete `Fst` `Snd` helytelen, a `fail` rendszer az utasítást használja, hogy a teszt sikertelen legyen.</span><span class="sxs-lookup"><span data-stu-id="78913-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
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

<span data-ttu-id="78913-121">Összetettebb feltételek ellenőrizhetők a szabványos könyvtárak útmutatójának [tesztelés szakaszában](xref:microsoft.quantum.libraries.diagnostics) található módszerek használatával.</span><span class="sxs-lookup"><span data-stu-id="78913-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="78913-122">Például a következő teszt ellenőrzi, hogy a `H(q); X(q); H(q);` hívása <xref:microsoft.quantum.canon.applywith> ugyanaz, mint a `Z(q)` .</span><span class="sxs-lookup"><span data-stu-id="78913-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="78913-123">Új funkciók hozzáadásakor érdemes új teszteket is felvenni, hogy az Ön hozzájárulása valóban a kívánt módon legyen.</span><span class="sxs-lookup"><span data-stu-id="78913-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="78913-124">Ez segíti a Közösség többi részét a funkció fenntartásában és fejlesztésében, és különösen segít más fejlesztőknek, hogy a szolgáltatásra támaszkodni tudjanak.</span><span class="sxs-lookup"><span data-stu-id="78913-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="78913-125">Ez fordítva is működik.</span><span class="sxs-lookup"><span data-stu-id="78913-125">This works the other way around, too!</span></span>
> <span data-ttu-id="78913-126">Ha van olyan meglévő szolgáltatás, amely néhány tesztet tartalmaz, akkor a tesztelési lefedettség hozzáadásával nagy mértékben járulhat hozzá a Közösséghez.</span><span class="sxs-lookup"><span data-stu-id="78913-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="78913-127">A helyszíni tesztek a Visual Studio test Explorer vagy a parancs használatával is futtathatók `dotnet test` , így a lekéréses kérelem megnyitása előtt ellenőrizheti a hozzájárulását.</span><span class="sxs-lookup"><span data-stu-id="78913-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="78913-128">Ha elutasítja a lekéréses kérelmet</span><span class="sxs-lookup"><span data-stu-id="78913-128">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="78913-129">Időnként elutasítja a hozzájárulás lekérését.</span><span class="sxs-lookup"><span data-stu-id="78913-129">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="78913-130">Ha ez történik, ez nem jelenti azt, hogy rossz, mert számos oka lehet annak, hogy nem tudjuk elfogadni az adott hozzájárulást.</span><span class="sxs-lookup"><span data-stu-id="78913-130">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="78913-131">Talán a legtöbb esetben a kvantum-programozási Közösséghez való hozzájárulás egy nagyon jó, de a Quantum Development Kit-Tárházak nem a megfelelő hely a fejlesztéshez.</span><span class="sxs-lookup"><span data-stu-id="78913-131">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="78913-132">Ilyen esetekben javasoljuk, hogy saját tárházat---a Quantum Development Kit erősségének részeként, hogy a saját kódtárak egyszerűen elkészíthetők és elterjeszthetők a GitHub és a NuGet.org használatával, ugyanúgy, ahogy a Canon és a vegyipari könyvtárakat is forgalmazni fogjuk.</span><span class="sxs-lookup"><span data-stu-id="78913-132">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="78913-133">Máskor elutasítottuk a jó hozzájárulást, mivel még nem áll készen a karbantartásra és a fejlesztésre.</span><span class="sxs-lookup"><span data-stu-id="78913-133">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="78913-134">Nehéz lehet mindent megtenni, ezért tervezzük meg, hogy milyen funkciókra van lehetőségünk a legjobb megoldásként.</span><span class="sxs-lookup"><span data-stu-id="78913-134">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="78913-135">Ez lehet egy másik eset, amikor egy funkciót külső gyártótól származó könyvtárként szabadít fel.</span><span class="sxs-lookup"><span data-stu-id="78913-135">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="78913-136">Azt is megteheti, hogy segít a szolgáltatás módosításában, hogy jobban illeszkedjen az ütemtervhez, hogy a lehető legjobb munkát végezzük.</span><span class="sxs-lookup"><span data-stu-id="78913-136">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="78913-137">A lekéréses kérelem módosításait is kérik, ha több dokumentációra vagy egységre vonatkozó tesztre van szükség, amely segít a használatában, vagy ha a többi könyvtárból nem tér el eléggé, akkor a Q# felhasználók megkereshetik a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="78913-137">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="78913-138">Ezekben az esetekben megpróbálunk néhány tanácsot készíteni a kód felülvizsgálatáról arról, hogy milyen felvehetők vagy módosíthatók, hogy a hozzájárulása könnyebb legyen a számunkra.</span><span class="sxs-lookup"><span data-stu-id="78913-138">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="78913-139">Végül a [Microsoft nyílt forráskódjának viselkedési szabályzatában](https://opensource.microsoft.com/codeofconduct/)ismertetett módon nem fogadhatunk olyan hozzájárulásokat, amelyek kárt okoznak a kvantum-számítástechnikai Közösség számára.</span><span class="sxs-lookup"><span data-stu-id="78913-139">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="78913-140">Szeretnénk biztosítani, hogy a hozzájárulások a teljes kvantum-számítástechnikai Közösséget, a jelenlegi csodálatos sokféleségben és a jövőben is kiszolgálják, ahogy az egyre nagyobb mértékben növekszik.</span><span class="sxs-lookup"><span data-stu-id="78913-140">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="78913-141">Nagyra értékeljük segítségét ennek a célnak a megvalósításában.</span><span class="sxs-lookup"><span data-stu-id="78913-141">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78913-142">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="78913-142">Next steps</span></span>

<span data-ttu-id="78913-143">Köszönjük, hogy a Quantum Development Kit nagyszerű erőforrást biztosít a teljes kvantum-programozási Közösség számára!</span><span class="sxs-lookup"><span data-stu-id="78913-143">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="78913-144">További információt a következő útmutatóban talál a Q# stílussal kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="78913-144">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78913-145">A Q# Style irányelvek ismertetése</span><span class="sxs-lookup"><span data-stu-id="78913-145">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="78913-146">Attól függően, hogy milyen kóddal járul hozzá, lehet, hogy további szempontokat is figyelembe kell vennie, amelyek segítségével a lehető legtöbb jót teheti a Közösségnek.</span><span class="sxs-lookup"><span data-stu-id="78913-146">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="78913-147">További tudnivalók a közreműködő mintákról</span><span class="sxs-lookup"><span data-stu-id="78913-147">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
