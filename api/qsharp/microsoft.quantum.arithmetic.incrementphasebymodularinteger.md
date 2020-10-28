---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721060"
---
# <a name="incrementphasebymodularinteger-operation"></a>IncrementPhaseByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Egy qubit-regiszter moduláris növekményét hajtja végre egy egész állandó értékkel.

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
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