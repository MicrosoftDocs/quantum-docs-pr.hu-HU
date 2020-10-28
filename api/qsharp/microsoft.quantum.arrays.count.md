---
uid: Microsoft.Quantum.Arrays.Count
title: Függvény száma
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719404"
---
# <a name="count-function"></a>Függvény száma

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, azaz, ha egy tömböt `'T[]` és egy predikátumot `'T -> Bool` is használhatunk az elemek szűréséhez.