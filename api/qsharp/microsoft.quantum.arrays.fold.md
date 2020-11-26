---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221164"
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