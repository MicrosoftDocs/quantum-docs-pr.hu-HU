---
uid: Microsoft.Quantum.Math.ModulusL
title: Modulus függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194933"
---
# <a name="modulusl-function"></a>Modulus függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kiszámítja a többrészes adatmennyiség kanonikus maradékát `value` `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Bevitel

### <a name="value--bigint"></a>érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A maradék kiszámításának értéke


### <a name="modulus--bigint"></a>modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A maradékok által elvégezhető modulusnak pozitívnak kell lennie



## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Egész szám $r $0 és között, `modulus - 1` amely a `value - r` modulus alapján osztható

## <a name="remarks"></a>Megjegyzések

Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig egy 0 és közötti pozitív egész szám `modulus - 1` , még akkor is, ha az érték negatív.