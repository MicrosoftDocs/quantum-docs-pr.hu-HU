---
title: 'A Microsoft Q # numerikus könyvtár használata'
description: Ismerje meg a Microsoft Quantum numerikus könyvtárában elérhető típusokat és műveleteket.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ad9f529efd06fdf13bab4467b091aafacf1d5b09
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907256"
---
# <a name="using-the-numerics-library"></a>A numerikus könyvtár használata

## <a name="overview"></a>Áttekintés

A numerikus könyvtár három összetevőből áll

1. **Alapszintű egész aritmetika** egész számokkal és összehasonlító értékekkel
1. Az alapszintű funkciókra épülő **magas szintű egész funkciók** ; többek között a szorzás, a osztás, az inverzió stb.  aláírt és aláíratlan egész számok esetén.
1. **Rögzített szintű aritmetikai funkciók** rögzített pontú inicializálással, hozzáadással, szorzással, kölcsönös, polinom értékeléssel és méréssel.

Ezen összetevők mindegyike egyetlen `open` utasítás használatával érhető el:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Típusok

A numerikus könyvtár a következő típusokat támogatja

1. **`LittleEndian`** : egy qubit tömb `qArr : Qubit[]`, amely egy egész számot jelöl, amelyben `qArr[0]` a legkevésbé jelentős bitet jelzi.
1. **`SignedLittleEndian`** : ugyanaz, mint `LittleEndian`, kivéve, hogy a két kiegészítésben tárolt, aláírt egész számot jelöli.
1. **`FixedPoint`** : egy qubit tömbből álló valós számot jelöl, `qArr2 : Qubit[]` és egy bináris pont `pos`, amely a bináris pont bal oldalán lévő bináris számjegyek számát számolja. a `qArr2` tárolása ugyanúgy történik, mint `SignedLittleEndian`.

## <a name="operations"></a>Műveletek

A fenti három típus mindegyikéhez számos művelet érhető el:

1. **`LittleEndian`**
    - Mellett
    - Összehasonlítás
    - Szorzás
    - Négyszögesítése
    - Osztás (a maradéktal)

1. **`SignedLittleEndian`**
    - Mellett
    - Összehasonlítás
    - A többverziós adattárház 2
    - Szorzás
    - Négyszögesítése

1. **`FixedPoint`**
    - Előkészítés/inicializálás klasszikus értékekre
    - Hozzáadás (klasszikus állandó vagy más kvantum rögzített pont)
    - Összehasonlítás
    - Szorzás
    - Négyszögesítése
    - Többfunkciós kiértékelés a páros és páratlan függvények esetében
    - Kölcsönös (1/x)
    - Mérés (klasszikus dupla)

Az egyes műveletekkel kapcsolatos további információkért és részletes dokumentációért tekintse meg a Q # Library dokumentációs dokumentumait a következő címen: [docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Minta: egész szám hozzáadása

Alapszintű példaként vegye fontolóra a $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $ értéket, amely egy n-qubit egész $x $ és egy n-vagy (n + 1) értékű művelet, amely a qubit regisztrálja $y $ bemenetként, amely az utóbbi, amelynek a összege a $ (x + y) $-ra van leképezve. Vegye figyelembe, hogy az összeg számítása $2 ^ n $, ha $y $ egy $n $ bites regisztrációban van tárolva.

A Quantum Development Kit használatával ez a művelet a következőképpen alkalmazható:
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Minta: simított függvények kiértékelése

Ha olyan simított függvényeket szeretne kiértékelni, mint például a $ \sin (x) $ a kvantum-számítógépen, ahol a $x $ a Quantum `FixedPoint` száma, a Quantum Development Kit numerikus könyvtára biztosítja az operatív `EvaluatePolynomialFxP` és `Evaluate[Even/Odd]PolynomialFxP`.

Az első, `EvaluatePolynomialFxP`lehetővé teszi, hogy kiértékelje a "$ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d, $ $, ahol $d $ a *mértéket*. Ehhez minden szükséges, hogy a polinom-`[a_0,..., a_d]` (típusú `Double[]`), a bemeneti `x : FixedPoint` és a kimeneti `y : FixedPoint` (kezdetben nulla):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
Az eredmény, $P (x) = 1 + 2x $, `yFxP`lesz tárolva.

A második, `EvaluateEvenPolynomialFxP`és a harmadik `EvaluateOddPolynomialFxP`a páros és páratlan függvények esetében is specializált. Ez a páros/páratlan függvény esetében $f (x) $ és $ $ P_ {even} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2D}, a $ $ $f (x) $ megközelítő értéke $P _ {even} (x) $ vagy $P _ {odd} (x): = x\cdot P_ {even} (x) $, ill.
A Q #-ban ez a két eset a következőképpen kezelhető:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
amely kiértékeli $P _ {even} (x) = 1 + 2x ^ 2 $ értéket, és
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
amely kiértékeli $P _ {odd} (x) = x + 2x ^ 3 $ értéket.

## <a name="more-samples"></a>További példák

További mintákat a [fő minták tárházában](https://github.com/Microsoft/Quantum)talál.

Első lépésként klónozott a tárházat, és nyissa meg a `Numerics` almappát:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Ezután `cd` az egyik minta mappájába, és futtassa a mintát a használatával

```bash
dotnet run
```
