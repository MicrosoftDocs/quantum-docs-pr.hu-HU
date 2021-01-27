---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 7bad044db9e2229c85cb3909dc4802bceaee6382
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847290"
---
# <a name="modulusi-function"></a>ModulusI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kiszámítja a többrészes adatmennyiség kanonikus maradékát `value` `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

A maradék kiszámításának értéke


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

A maradékok által elvégezhető modulusnak pozitívnak kell lennie



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Egész szám $r $0 és között, `modulus - 1` amely a `value - r` modulus alapján osztható

## <a name="remarks"></a>Megjegyzések

Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig nem negatív egész szám 0 és között `modulus - 1` , még akkor is, ha az érték negatív.