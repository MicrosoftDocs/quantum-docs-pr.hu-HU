---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 6a39ce49dfa28c1f1cbe6b29e526144c3ac19e53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222881"
---
# <a name="incrementphasebymodularinteger-operation"></a>IncrementPhaseByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy qubit-regiszter moduláris növekményét hajtja végre egy egész állandó értékkel.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

`increment`$A $, `modulus` $N $ és Integer szerint, $y $ kódolással jelezze nekünk `target` .
Ezután a művelet a következő átalakítást hajtja végre: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} egész számok kódolása kis endian formátumban történik QFT alapján.

## <a name="input"></a>Bevitel

### <a name="increment--int"></a>növekmény: [int](xref:microsoft.quantum.lang-ref.int)

$A $ számú növekményt $y $ értékre kell felvenni.


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

Egész $N $, hogy a mods $y + a $.


### <a name="target--phaselittleendian"></a>cél: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Egész $y $ a fázis-kódolású kis endian formátumban, amelyet `increment` a $a $ hozzáad a következőhöz:.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Feltételezi, hogy `target` a legmagasabb bit 0 értékű.
Azt is feltételezi, hogy a célként megadott érték kisebb, mint $N $.

Az áramköri diagramhoz és a magyarázathoz lásd az 5. ábrát a következő [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. aritmetika. IncrementByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)