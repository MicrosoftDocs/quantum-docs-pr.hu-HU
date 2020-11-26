---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 169326879919b5b72d600c33d624776b720cc6bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222592"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>MultiplyAndAddByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy qubit-regiszterben egy moduláris szorzást és-hozzáadást végez az egész számok állandói alapján.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

A $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ értéket implementálja egy adott modulus $N $, konstans szorzó $a $ és summand $y $ esetében.

## <a name="input"></a>Bevitel

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes alapállapotok címkéjébe felvenni $a $ értéket.


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

Az a modulus $N $, amelyet a Hozzáadás és a szorzás is figyelembe vesz a tekintetében.


### <a name="multiplier--littleendian"></a>szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Egy olyan előjel nélküli egész szám, amelynek értékét fel kell venni az egyes alapállapotok címkéjébe `summand` .


### <a name="summand--littleendian"></a>summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A művelet céljaként használandó, előjel nélküli egész számot jelölő kvantum-regisztráció.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

- Az áramköri diagramhoz és a magyarázathoz lásd a 6. ábrát a [arXiv 7. oldalán: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Ez a művelet megfelel a CMULT (a) MOD (N) [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. aritmetika. MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)