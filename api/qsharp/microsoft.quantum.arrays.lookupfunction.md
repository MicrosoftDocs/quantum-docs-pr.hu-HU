---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719069"
---
# <a name="lookupfunction-function"></a>LookupFunction függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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