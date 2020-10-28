---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Carry művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 2b977151861fb01be7d7dbad6e0a7b803fded880
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721312"
---
# <a name="carry-operation"></a>Carry művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Végrehajt egy reverzibilis Carry-kaput. A qubit-ben és a-ben két summand-ben kódolt, a és a alkalmazásban elvégezhető átviteli sebesség miatt a `carryIn` `summand1` `summand2` kiszámítja a bitenkénti és a `carryIn` `summand1` qubit, `summand2` `summand2` valamint a végrehajtást a xored qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="carryin--qubit"></a>carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Carry-in qubit.


### <a name="summand1--qubit"></a>summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Első summand qubit.


### <a name="summand2--qubit"></a>summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A második summand qubit a és a összegének alsó kis részébe kerül `summand1` `summand2` .


### <a name="carryout--qubit"></a>carryOut: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A végrehajtás qubit az összeg magasabb xored lesz.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

