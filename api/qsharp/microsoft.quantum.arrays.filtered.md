---
uid: Microsoft.Quantum.Arrays.Filtered
title: Szűrt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847164"
---
# <a name="filtered-function"></a>Szűrt függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömb és egy, a tömb elemeihez definiált predikátum miatt egy tömböt ad vissza, amely a predikátumnak megfelelő elemeket tartalmaz.

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="predicate--t---bool"></a>predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)

Az `'T` elemek szűréséhez használt logikai értékből származó függvény.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--t"></a>Kimenet: 'T []

`'T[]`A predikátumnak megfelelő elemek tömbje.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

A következő kód a "szűrt" függvényt mutatja be.
A predikátum a függvény használatával van definiálva @"microsoft.quantum.logical.greaterthani" :

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

Ennek a példának a várt eredménye egy 5-nél nagyobb számok tömbje lesz.

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.