---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848525"
---
# <a name="indexof-function"></a>IndexOf függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Példa

Tegyük fel, hogy `IsEven : Int -> Bool` egy olyan függvény, amely `true` csak akkor adja vissza, ha a bemenete páros. Ezt követően a használatával `IndexOf` megkeresheti a tömb első páros elemét is:

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```