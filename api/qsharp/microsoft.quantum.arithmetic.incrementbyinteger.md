---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721109"
---
# <a name="incrementbyinteger-operation"></a>IncrementByInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Megnöveli egy előjel nélküli kvantum-regisztrációt egy klasszikus egész számmal, fázisok forgása alapján.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

