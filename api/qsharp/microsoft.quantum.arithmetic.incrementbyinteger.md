---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fa5e75e91206aa5f33233c8a54d6e9e7ac2950e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222966"
---
# <a name="incrementbyinteger-operation"></a>IncrementByInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Megnöveli egy előjel nélküli kvantum-regisztrációt egy klasszikus egész számmal, fázisok forgása alapján.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Tegyük fel, hogy az `target` előjel nélküli egész $x $ endian kódolásban kódolja, és a `increment` $a $ értékkel egyenlő.
Ezt követően ez a művelet megvalósítja az egységes $ \ket{x} \mapsto \ket{x + a} $ értéket, ahol a Hozzáadás a maradékot a 2. számú ^ n $, ahol a $n = \texttt{Length (TARGET!)} $.

## <a name="input"></a>Bevitel

### <a name="increment--int"></a>növekmény: [int](xref:microsoft.quantum.lang-ref.int)

Az az egész szám, amelynek a `target` értéke növekszik.


### <a name="target--littleendian"></a>cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A kvantum-regisztráció előjel nélküli egész számot használ kis endian kódolással.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

