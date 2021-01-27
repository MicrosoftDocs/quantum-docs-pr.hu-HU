---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848006"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Létrehoz egy blokk-Encoding egységes Hamilton.

A Hamilton $H = \ sum_ {j} \ alpha_j P_j $ kifejezést $P _j $ értékkel rendelkező, az összes valós hatékonyságú $ \ alpha_j $ nevű összeg írja le.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Bevitel

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` amely a $H $-t írja le a Pauli-kifejezések összegeként



## <a name="output--doubleblockencodingreflection"></a>Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Első paraméter

Az együtthatók egy normája: $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Második paraméter

A `BlockEncodingReflection` Hamilton egységes $U $ $H $. Mivel ez az egységes megfelel a $U ^ 2 = I $-nek, azt is tükrözi.

## <a name="remarks"></a>Megjegyzések

Ezt a rendszer a $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ állapotának előkészítésével és előkészítésével, valamint a szorzás által vezérelt egységes és a létrehozásával szerzi be <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .