---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: _JordanWignerClusterOperatorImpl művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9a01742f25790e32d1787cc6cc266407de909c16
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215741"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a>_JordanWignerClusterOperatorImpl művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A dinamikus generátort szimulálható kapuk készlete jelöli, a JordanWigner pedig kibővíthető.

További részletekért lásd a [Dynamic Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) című témakört.

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Egy, az JordanWigner-ben egységes evolúcióként megjeleníteni kívánt generátor-index.


### <a name="stepsize--double"></a>stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

A szimulációs algoritmusok aláírásának megfelelő dummy változó.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A regisztráció az idő-Evolution operátorral végezhető el.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

