---
uid: Microsoft.Quantum.Intrinsic.R
title: R-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720929"
---
# <a name="r-operation"></a>R-művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag [](https://nuget.org/packages/)


A megadott Pauli-tengely elforgatását alkalmazza.

\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align}, ahol $ \mu \in \{ i, X, Y, Z \} $.

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A "Pauli" operátor ($ \mu $) exponentiated kell lennie a forgatás létrehozásához.


### <a name="theta--double"></a>THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a szög, amely alapján a qubit el kell forgatni.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

A Qubit, amelyre a kaput alkalmazni kell.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A szolgáltatással való híváskor a `pauli = PauliI` művelet *globális szakaszt* alkalmaz. Ez a fázis jelentős lehet, ha az elválasztó használatával használja `Controlled` .