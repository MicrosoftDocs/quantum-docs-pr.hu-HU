---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846494"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A qubit-regiszterben egy egész állandó használatával hajtja végre a moduláris szorzást.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

`modulus`$N $ és $a $ jelöléssel jelezze nekünk `constMultiplier` .
Ezt követően a művelet egy egységes műveletet valósít meg, amelyet a következő Térkép határoz meg a számítási alapon: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ az összes $y $ és a $N-$1 $0 között.

## <a name="input"></a>Bevitel

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Az állandó, amellyel a szorzót megszorozzuk. A modulus értékének együtt kell lennie.


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

A szorzási művelet elvégzése többértékű `modulus` .


### <a name="multiplier--littleendian"></a>szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A szám egy állandóval megszorozva.
Ez egy qubits-kódolású tömb, amely egy egész szám endian formátumú.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

- Az áramköri diagramhoz és a magyarázathoz lásd a 7. ábrán a [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Ez a művelet megfelel az U ₐ a [arXiv-ben: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)