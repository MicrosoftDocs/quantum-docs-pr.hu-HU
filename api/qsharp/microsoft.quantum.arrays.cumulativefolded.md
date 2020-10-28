---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719393"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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