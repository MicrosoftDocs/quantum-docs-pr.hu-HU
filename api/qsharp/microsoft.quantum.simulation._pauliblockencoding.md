---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710659"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding függvény

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


Létrehoz egy blokk-Encoding egységes Hamilton.

A Hamilton $H = \ sum_ {j} \ alpha_j P_j $ kifejezést $P _j $ értékkel rendelkező, az összes valós hatékonyságú $ \ alpha_j $ nevű összeg írja le.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Bevitel

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` amely a $H $-t írja le a Pauli-kifejezések összegeként


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

Egy egységes művelet $V $, amely a (z) $ \ket{j} $ indexbe tartozó egységes $V _j $-ra van alkalmazva, a függvény $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a>multiplexer: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL





## <a name="output--doubleblockencodingreflection"></a>Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Első paraméter

Az együtthatók egy normája: $ \alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Második paraméter

A `BlockEncodingReflection` Hamilton egységes $U $ $U $. Mivel ez az egységes megfelel a $U ^ 2 = I $-nek, azt is tükrözi.

## <a name="remarks"></a>Megjegyzések

Példa a műveletekre: az állapot előkészítése és elkészítése a $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, valamint egy szorzásra vezérelt, egységes <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> és <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .