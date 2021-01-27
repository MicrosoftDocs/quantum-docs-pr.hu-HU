---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: a64ac3970e3e67568f91b4e67775d834a80c04a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835715"
---
# <a name="estimateenergy-operation"></a>EstimateEnergy művelet

Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


A molekula energia-becslését az egyes Jordan-Wigner feltételek által biztosított energia összegzésével számítja ki.

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>Leírás

Ez a művelet implicit módon támaszkodik a felpörgetéses indexelési konvencióra.

## <a name="input"></a>Bevitel

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

A Jordan-Wigner Hamilton.


### <a name="nsamples--int"></a>nSamples: [int](xref:microsoft.quantum.lang-ref.int)

A várakozási feltételek becsléséhez használandó minták száma.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

A molekula becsült energiája