---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722800"
---
# <a name="_jwoptimizedfermionevolution-operation"></a>_JWOptimizedFermionEvolution művelet

Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)

Csomag [](https://nuget.org/packages/)


A dinamikus generátort szimulálható kapuk készlete jelöli, a JWOptimized pedig kibővíthető.

További részletekért lásd a [Dynamic Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) című témakört.

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Az JWOptimized-alapú, egységes evolúcióként megjelenítendő generátor-index.


### <a name="stepsize--double"></a>stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)

Egy szorzó az időpontra, amely a (z)-ben hivatkozott kifejezés alapján alakul `generatorIndex` .


### <a name="parityqubit--qubit"></a>parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, amely meghatározza a Time-Evolution előjelét.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A regisztráció az idő-Evolution operátorral végezhető el.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

