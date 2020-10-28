---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713725"
---
# <a name="estimatetermexpectation-operation"></a>EstimateTermExpectation művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Csomag [](https://nuget.org/packages/)


Egy adott Jordan-Wigner Hamilton-kifejezéshez társított energia kiszámítása

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Leírás

Ez a művelet becslést készít az egyes mérési operátorokhoz társított elvárások értékéről, és a mintavételezéssel megszorozza azt a megfelelő együtthatóval.
Az eredmények egy olyan változóba vannak összesítve, amely a Jordan-Wigneri időszak energiafogyasztását tartalmazza.

## <a name="input"></a>Bevitel

### <a name="inputstateunitary--qubit--unit-adj"></a>inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj

Az állapot előkészítéséhez használt egységes szolgáltatás.


### <a name="ops--pauli"></a>Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

A Jordan-Wigner kifejezés mérési operátorai.


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

A Jordan-Wigner kifejezés együtthatói.


### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

A molekuláris rendszerek szimulálásához szükséges qubits száma.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

A kifejezés elvárt értékének becsléséhez használandó minták száma.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

Az Jordan-Wigner-kifejezéshez kapcsolódó energia.