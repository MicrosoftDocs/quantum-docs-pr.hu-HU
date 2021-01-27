---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Sum művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847756"
---
# <a name="sum-operation"></a>Sum művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy reverzibilis összegű kaput implementál. A qubit-ben és a-ben két summand-ben kódolt, a és a rendszerbe bejelentkezett, a ( `carryIn` `summand1` bitenkénti) és a `summand2` `carryIn` `summand1` `summand2` qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="carryin--qubit"></a>carryIn: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Carry-in qubit.


### <a name="summand1--qubit"></a>summand1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Első summand qubit.


### <a name="summand2--qubit"></a>summand2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A második summand qubit a és a összegének alsó kis részébe kerül `summand1` `summand2` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A `Carry` művelettel ellentétben ez nem számítja ki a végrehajtáshoz szükséges biteket.