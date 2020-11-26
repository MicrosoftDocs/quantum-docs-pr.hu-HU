---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: bd182ea50d747e07bb0f8051c5dbc128b7ff7674
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198639"
---
# <a name="rfrac-operation"></a>RFrac művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A megadott Pauli-tengely rotációját alkalmazza egy dyadic-frakcióként megadott szögben.

\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align}, ahol $ \mu \in \{ i, X, Y, Z \} $.

> [!WARNING]
> Ez a művelet a következővel **ellentétes** aláírási konvenciót használja: @"microsoft.quantum.intrinsic.r" .

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A Pauli operátornak exponentiated kell lennie az elforgatás megalkotása érdekében.


### <a name="numerator--int"></a>számláló: [int](xref:microsoft.quantum.lang-ref.int)

A számláló azon szög dyadic-frakciójának ábrázolása, amellyel a qubit el kell forgatni.


### <a name="power--int"></a>teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)

A két ereje annak a szögnek a nevezőjét határozza meg, amellyel a qubit el kell forgatni.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

A Qubit, amelyre a kaput alkalmazni kell.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Egyenértékű a következővel:

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```