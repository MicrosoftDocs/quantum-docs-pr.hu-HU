---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720904"
---
# <a name="r1frac-operation"></a>R1Frac művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag [](https://nuget.org/packages/)


A $ \ket $ állapotú rotációt alkalmazza egy {1} dyadic-frakcióként megadott szögben.

\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \pi k/2 ^ n}).
\end{align}

> [!WARNING]
> Ezzel a művelettel a-től **eltérő aláírási** konvenciót használ @"microsoft.quantum.intrinsic.r" , és nem tartalmazza a következőhöz tartozó $1/2 $ faktort: @"microsoft.quantum.intrinsic.r1" .

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Bevitel

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
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```