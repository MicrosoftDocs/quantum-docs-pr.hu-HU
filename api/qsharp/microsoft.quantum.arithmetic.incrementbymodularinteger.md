---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 8a02d22facce8f58180752b6d063ac55d75ca537
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222949"
---
# <a name="incrementbymodularinteger-operation"></a>IncrementByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy qubit-regiszter moduláris növekményét hajtja végre egy egész állandó értékkel.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

`increment`$A $, `modulus` $N $ és Integer szerint, $y $ kódolással jelezze nekünk `target` .
Ezután a művelet a következő átalakítást hajtja végre: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} egész számok kódolása kis endian formátumban történik.

## <a name="input"></a>Bevitel

### <a name="increment--int"></a>növekmény: [int](xref:microsoft.quantum.lang-ref.int)

$A $ számú növekményt $y $ értékre kell felvenni.


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

Egész $N $, hogy a mods $y + a $.


### <a name="target--littleendian"></a>cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Egész szám $y $ `LittleEndian` formátumban, amelyet `increment` $a $ hozzáad a következőhöz:.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Feltételezi, hogy a célként megadott kezdeti érték kisebb, mint $N $, és hogy a növekmény $a $ értéke kisebb, mint $N $.
Figyelje meg, hogy <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> ugyanazokat a műveleteket hajtja végre `PhaseLittleEndian` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. aritmetika. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)