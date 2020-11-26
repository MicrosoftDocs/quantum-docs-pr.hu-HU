---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222915"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Megnöveli egy előjel nélküli kvantum-regisztrációt egy klasszikus egész számmal, fázisok forgása alapján.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Tegyük fel, hogy az `target` előjel nélküli egész $x $ endian kódolásban kódolja, és a `increment` $a $ értékkel egyenlő.
Ezt követően ez a művelet megvalósítja az egységes $ \ket{x} \mapsto \ket{x + a} $ értéket, ahol a Hozzáadás a maradékot a 2. számú ^ n $, ahol a $n = \texttt{Length (TARGET!)} $.

## <a name="input"></a>Bevitel

### <a name="increment--int"></a>növekmény: [int](xref:microsoft.quantum.lang-ref.int)

Az az egész szám, amelynek a `target` értéke növekszik.


### <a name="target--phaselittleendian"></a>cél: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

A kvantum-regisztrálás egy előjel nélküli egész számot használ a endian kódolással a kettős (QFT) alapon.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Vegye figyelembe, hogy egyszerűsítettük az áramkört, mert a növekmény egy klasszikus állandó, nem pedig a kvantum-regisztráció.

Tekintse meg a [ arXiv: Quant-pH/0008033v1 6. oldalának ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) ábráját az áramköri diagramhoz és magyarázathoz.

## <a name="references"></a>Hivatkozások

- [*Thomas G. drapérier*, arXiv: Quant – pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. aritmetika. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)