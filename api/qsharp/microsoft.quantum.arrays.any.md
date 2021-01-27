---
uid: Microsoft.Quantum.Arrays.Any
title: Bármely függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846283"
---
# <a name="any-function"></a>Bármely függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A tömb elemeihez megadott tömb és predikátum alapján a rendszer ellenőrzi, hogy a tömb legalább egy eleme megfelel-e a predikátumnak.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Bevitel

### <a name="predicate--t---bool"></a>predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)

Az `'T` `Bool` elemekhez tartozó függvény, amely az elemek vizsgálatára szolgál.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Az `Bool` összes elemre alkalmazott PREDIKÁTUM vagy függvényének értéke.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, például ha egy tömb `'T[]` és egy függvény is létrehoz `predicate: 'T -> Bool` egy `Bool` értéket, amely azt jelzi, hogy egyes elemek megfelelnek-e `predicate` .