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
# <a name="contributing-code"></a>Közreműködő kód #

A hibák jelentése és a dokumentáció fejlesztése mellett a kód a Quantum Development Kit-hez való hozzájárulása is nagyon közvetlen módja lehet a vállalatoknak a kvantum-programozási Közösségben.
A kód hozzájárulásával segíthet a problémák megoldásában, új példák megadásában, a meglévő kódtárak használatának megkönnyítésében, vagy akár teljesen új funkciók hozzáadásában is.

Ebben az útmutatóban részletesen ismertetjük, hogy mi a teendő, ha áttekintjük a lekéréses kérelmeket, hogy a lehető legjobb segítséget nyújtson.

## <a name="what-we-look-for"></a>Mit keresünk ##

Az ideális kód hozzájárulása a Quantum Development Kit-adattár meglévő munkája alapján javítja ki a problémákat, kibővítheti a meglévő funkciókat, vagy hozzáadhat új szolgáltatásokat, amelyek egy adattár hatókörén belül találhatók.
Ha elfogadjuk a kód bevonását, az a Quantum Development Kit részévé válik, így az új funkciók ugyanúgy lesznek felszabadítva, karbantartva és kifejlesztve, mint a Quantum Development Kit többi része.
Így hasznos lehet, ha a hozzájárulás által hozzáadott funkciók jól teszteltek és dokumentálva vannak.

### <a name="unit-tests"></a>Egység tesztek ###

A Q # functions, Operations és felhasználó által definiált típusokat, amelyek a tárakat (például a canonot) a fejlesztés részeként automatikusan tesztelik a [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) adattárban.
Új lekéréses kérelem megnyitásakor – például az Azure- [folyamatok](https://azure.microsoft.com/services/devops/pipelines/) konfigurációjában – a lekéréses kérelem módosításai nem bontják le azokat a meglévő funkciókat, amelyekre a Quantum programozási Közösség függ.
Ezek a tesztek a [Microsoft. Quantum. xUnit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) csomag használatával íródnak, amely a Q # függvényeket és műveleteket teszteli a [xUnit](https://xunit.github.io/) -keretrendszer számára.

A [`Standard/tests/Standard.Tests.csproj`](https://github.com/microsoft/QuantumLibraries/blob/master/Standard/tests/Standard.Tests.csproj) ezt a xUnit-integrációt használja a `Test`-ban végződő függvények vagy műveletek futtatásához.
A következő függvény például annak biztosítására szolgál, hogy a <xref:microsoft.quantum.canon.fst> és a <xref:microsoft.quantum.canon.snd> függvény a megfelelő kimeneteket adja vissza egy reprezentatív példában.
Ha a `Fst` vagy `Snd` kimenete helytelen, a rendszer a `fail` utasítást használja, hogy a teszt sikertelen legyen.

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

Összetettebb feltételek ellenőrizhetők a szabványos könyvtárak útmutatójának [tesztelés szakaszában](xref:microsoft.quantum.libraries.diagnostics) található módszerek használatával.
A következő teszt például azt ellenőrzi, hogy a `H(q); X(q); H(q);`, ahogyan az <xref:microsoft.quantum.canon.applywith> meghívja a `Z(q)`.

```qsharp
operation WithTest () : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

Új funkciók hozzáadásakor érdemes új teszteket is felvenni, hogy az Ön hozzájárulása valóban a kívánt módon legyen.
Ez segíti a Közösség többi részét a funkció fenntartásában és fejlesztésében, és különösen segít más fejlesztőknek, hogy a szolgáltatásra támaszkodni tudjanak.

> [!NOTE]
> Ez fordítva is működik.
> Ha van olyan meglévő szolgáltatás, amely néhány tesztet tartalmaz, akkor a tesztelési lefedettség hozzáadásával nagy mértékben járulhat hozzá a Közösséghez.

A helyszíni tesztek a Visual Studio test Explorer vagy a `dotnet test` paranccsal is futtathatók, így a lekéréses kérelem megnyitása előtt ellenőrizheti a hozzájárulását.

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="when-well-reject-a-pull-request"></a>Ha elutasítja a lekéréses kérelmet ##

Időnként elutasítja a hozzájárulás lekérését.
Ha ez történik, ez nem jelenti azt, hogy rossz, mert számos oka lehet annak, hogy nem tudjuk elfogadni az adott hozzájárulást.
Talán a legtöbb esetben a kvantum-programozási Közösséghez való hozzájárulás egy nagyon jó, de a Quantum Development Kit-Tárházak nem a megfelelő hely a fejlesztéshez.
Ilyen esetekben arra törekszünk, hogy saját tárházat---a Quantum Development Kit erősségének részeként, hogy könnyen elvégezhető és terjeszthető legyen a saját könyvtárai a GitHub és a NuGet.org használatával, ugyanúgy, ahogy a Canon és a kémia is kiterjeszthető. tárak ma.

Máskor elutasítottuk a jó hozzájárulást, mivel még nem áll készen a karbantartásra és a fejlesztésre.
Nehéz lehet mindent megtenni, ezért tervezzük meg, hogy milyen funkciókra van lehetőségünk a legjobb megoldásként.
Ez lehet egy másik eset, amikor egy funkciót külső gyártótól származó könyvtárként szabadít fel.
Azt is megteheti, hogy segít a szolgáltatás módosításában, hogy jobban illeszkedjen az ütemtervhez, hogy a lehető legjobb munkát végezzük.

A lekéréses kérelem módosításait is kérik, ha több dokumentációra vagy egységre vonatkozó tesztre van szükség, amely segít a használatában, vagy ha a Q # könyvtáraiban lévő többitől függően nem elég, hogy a felhasználók megtalálják a funkciót.
Ezekben az esetekben megpróbálunk néhány tanácsot készíteni a kód felülvizsgálatáról arról, hogy milyen felvehetők vagy módosíthatók, hogy a hozzájárulása könnyebb legyen a számunkra.

Végül a [Microsoft nyílt forráskódjának viselkedési szabályzatában](https://opensource.microsoft.com/codeofconduct/)ismertetett módon nem fogadhatunk olyan hozzájárulásokat, amelyek kárt okoznak a kvantum-számítástechnikai Közösség számára.
Szeretnénk biztosítani, hogy a hozzájárulások a teljes kvantum-számítástechnikai Közösséget, a jelenlegi csodálatos sokféleségben és a jövőben is kiszolgálják, ahogy az egyre nagyobb mértékben növekszik.
Nagyra értékeljük segítségét ennek a célnak a megvalósításában.

## <a name="next-steps"></a>Következő lépések ##

Köszönjük, hogy a Quantum Development Kit nagyszerű erőforrást biztosít a teljes kvantum-programozási Közösség számára!
További információért folytassa a következő útmutatóval a Q # Style-on.

> [!div class="nextstepaction"]
> [A Q # Style irányelvek ismertetése](xref:microsoft.quantum.contributing.style)
