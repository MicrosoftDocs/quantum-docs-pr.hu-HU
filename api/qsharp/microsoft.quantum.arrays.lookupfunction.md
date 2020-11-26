---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220773"
---
# <a name="lookupfunction-function"></a>LookupFunction függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A tömb adott értéke egy olyan függvényt ad vissza, amely a tömb elemeit adja vissza.

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>Bevitel

### <a name="array--t"></a>tömb: 'T []

Az a tömb, amelyet keresési függvényként kell megjeleníteni.



## <a name="output--int---t"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int) -> 't

Ilyen függvény `f` `f(idx) == f[idx]` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A tömb azon elemeinek típusa, amelyek keresési függvényként jelennek meg.

## <a name="remarks"></a>Megjegyzések

Ez a függvény elsősorban olyan függvényekkel és műveletekkel való együttműködésre hasznos, amelyek `Int -> 'T` argumentumként működnek. Ez gyakran előfordul, például a Generator reprezentációs könyvtárban, ahol a függvények használatával elkerülhető, hogy a teljes tömb ne legyen rögzítve a memóriában.