---
uid: Microsoft.Quantum.Arrays.Sorted
title: Rendezett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845445"
---
# <a name="sorted-function"></a>Rendezett függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömb esetében a tömb azon elemeit adja vissza, amelyek egy adott összehasonlító függvény szerint vannak rendezve.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="comparison--tt---bool"></a>összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)

Olyan függvény, amely összehasonlítja a két olyan elemet, amely az IF értéknél `a` kisebb vagy azzal egyenlő `b` `comparison(a, b)` `true` .


### <a name="array--t"></a>tömb: 'T []

A rendezendő tömb.



## <a name="output--t"></a>Kimenet: 'T []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes elemeinek típusa `array` .

## <a name="example"></a>Példa

Az alábbi kódrészlet egy egész számokból álló tömböt rendez, amely növekvő sorrendben történik:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Megjegyzések

`comparison`Feltételezzük, hogy a függvény tranzitív, például ha a `comparison(a, b)` és a `comparison(b, c)` , akkor `comparison(a, c)` feltételezzük. Ha ez a tulajdonság nem áll fenn, akkor előfordulhat, hogy a függvény kimenete helytelen.

Mivel ez egy függvény, az eredmények teljesen determinstic, még akkor is, ha két elem egyenlőnek számít, `comparison` azaz, hogy mikor `comparison(a, b)` és `comparison(b, a)` mindkettőben `true` .
Különösen a függvény által végrehajtott rendezés garantáltan stabilnak minősül, így ha két elem van `a` `b` , és a sorrendben történik `array` , és a értéke a következő `comparison` , akkor `a` a kimenet előtt is megjelenik `b` .

Például:

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```