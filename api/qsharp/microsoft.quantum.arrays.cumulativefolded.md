---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846245"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A leképezett és a fold egyetlen függvénybe való egyesítése

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Leírás

Ez a függvény `fn` a tömbön keresztül ismétli meg a függvényt, kezdve a kezdeti állapottól, `state` és az összes köztes értéket adja vissza, nem tartalmazza a kezdeti állapotot.

## <a name="input"></a>Bevitel

### <a name="fn--statet---state"></a>FN: (' State, 'T)-> ' állapot

A tömbben hajtogatható függvény


### <a name="state--state"></a>állapot: "állapot

Az eldobni kívánt kezdeti állapot


### <a name="array--t"></a>tömb: 'T []

Az áthajtogatható értékek tömbje



## <a name="output--state"></a>Kimenet: "State []

Az összes köztes állapot, beleértve a végső állapotot, de nem a kezdeti állapotot.
A kimeneti tömb hossza megegyezik a hosszával `array` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="state"></a>"Állapot

A függvény által működtetett állapotok típusa `fn` , azaz az első bemenetként fogadja, és visszaadja.
### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```