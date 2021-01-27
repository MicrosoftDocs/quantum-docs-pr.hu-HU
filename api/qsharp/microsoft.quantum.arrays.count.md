---
uid: Microsoft.Quantum.Arrays.Count
title: Függvény száma
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: e178ee63526e3485e8cc83a3ba8f827d8ecac552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842838"
---
# <a name="count-function"></a>Függvény száma

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömb és egy olyan predikátum, amely a tömb elemeihez van meghatározva, az elemek számát adja vissza, amely a predikátumnak megfelelő elemeket tartalmaz.

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="predicate--t---bool"></a>predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)

Az `'T` elemek szűréséhez használt logikai értékből származó függvény.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Azon elemek száma, `array` amelyek megfelelnek a predikátumnak.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

A következő kód a "Count" függvényt mutatja be.
A predikátum a függvény használatával van definiálva @"microsoft.quantum.logical.greaterthani" :

```qsharp
 let predicate = GreaterThanI(_, 5);
 let count = Count(predicate, [2, 5, 9, 1, 8]);
 // count = 2
```

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.