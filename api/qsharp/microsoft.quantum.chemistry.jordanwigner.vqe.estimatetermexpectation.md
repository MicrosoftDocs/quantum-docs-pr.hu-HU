---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835673"
---
# <a name="estimatetermexpectation-operation"></a>EstimateTermExpectation művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Egy adott Jordan-Wigner Hamilton-kifejezéshez társított energia kiszámítása

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Leírás

Ez a művelet becslést készít az egyes mérési operátorokhoz társított elvárások értékéről, és a mintavételezéssel megszorozza azt a megfelelő együtthatóval.
Az eredmények egy olyan változóba vannak összesítve, amely a Jordan-Wigneri időszak energiafogyasztását tartalmazza.

## <a name="input"></a>Bevitel

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

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