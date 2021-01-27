---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848689"
---
# <a name="equala-function"></a>Equala függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Adott típusú két tömb, valamint egy, a tömbök elemeihez definiált predikátum is ellenőrzi, hogy a tömbök egyenlőek-e.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Bevitel

### <a name="equal--tt---bool"></a>egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)

A rekordból egy függvény, amely azt vizsgálja, hogy a `('T, 'T)` `Bool` tömbök két eleme egyenlő-e.


### <a name="array1--t"></a>tömb1: nem []

Az elsőként összehasonlítható tömb.


### <a name="array2--t"></a>tömb2: nem []

Az összehasonlítandó második tömb.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Az érték `true` , ha és csak akkor, ha `array1` és `array2` egyenlő.
Vagyis ha mindkét tömb azonos hosszúságú, és az összes elem megegyezik a által meghatározott értékkel `equal` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes tömbök elemeinek típusa.

## <a name="example"></a>Példa

A következő kód ellenőrzi, hogy a tömbök különböző párjai egyenlőek-e:

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>Megjegyzések

Ez a függvény általános típusokhoz van definiálva; azaz, ha két tömb `'T[]` és egy függvény van `equal: ('T, 'T) -> Bool` , akkor ez a függvény egy értéket ad vissza, `Bool` amely jelzi, hogy a tömbök egyenlőek-e.
Ha két tömbnek egyenlőnek kell lennie, akkor egyenlőnek kell lennie, és a tömbök azonos helyein lévő elemeknek egyenlőnek kell lenniük.