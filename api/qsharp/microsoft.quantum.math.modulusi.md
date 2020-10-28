---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723094"
---
# <a name="modulusi-function"></a>ModulusI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


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

Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig egy 0 és közötti pozitív egész szám `modulus - 1` , még akkor is, ha az érték negatív.