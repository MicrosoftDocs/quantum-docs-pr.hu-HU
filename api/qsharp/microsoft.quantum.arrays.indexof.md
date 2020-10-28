---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719176"
---
# <a name="indexof-function"></a>IndexOf függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy olyan tömb első elemének első indexét adja vissza, amely megfelel egy adott predikátumnak. Ha nem létezik ilyen elem, a a-1 értéket adja vissza.

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="predicate--t---bool"></a>predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)

Egy predikátum-függvény, amely a tömb elemein működik.


### <a name="arr--t"></a>ARR: 'T []

A megadott predikátum használatával keresendő tömb.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Vagy a legkisebb index `idx` , amely `predicate(arr[idx])` igaz, vagy-1, ha nincs ilyen elem.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

