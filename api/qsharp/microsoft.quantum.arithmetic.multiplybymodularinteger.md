---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719789"
---
# <a name="multiplybymodularinteger-operation"></a>MultiplyByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


A qubit-regiszterben egy egész állandó használatával hajtja végre a moduláris szorzást.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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