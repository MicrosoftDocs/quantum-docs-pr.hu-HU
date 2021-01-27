---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848607"
---
# <a name="fold-function"></a>Fold függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Megismétli a függvényt `f` egy tömbön keresztül `array` , visszatérve `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Bevitel

### <a name="folder--statet---state"></a>mappa: ("állapot, nem) – >" állapot

A tömbben hajtogatható függvény.


### <a name="state--state"></a>állapot: "állapot

A mappa kezdeti állapota.


### <a name="array--t"></a>tömb: 'T []

Az áthajtogatható értékek tömbje.



## <a name="output--state"></a>Kimenet: "State

A mappa által a összes elemének megismétlése után visszaadott végső állapot `array` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="state"></a>"Állapot

A függvény által működtetett állapotok típusa `folder` , azaz az első argumentumként fogadja el az értéket, és visszaadja.
### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```