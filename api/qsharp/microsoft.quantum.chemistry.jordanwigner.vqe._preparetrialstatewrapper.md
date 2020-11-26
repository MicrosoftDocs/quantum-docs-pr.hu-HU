---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: 8e1a39cbd307a467ab7f0466c90722e1c8c46d4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224683"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="70d07-102">_prepareTrialStateWrapper művelet</span><span class="sxs-lookup"><span data-stu-id="70d07-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="70d07-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="70d07-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="70d07-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="70d07-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="70d07-105">A PrepareTrialState körüli privát burkoló egy adjoint definiálásával teszi kompatibilisvé a EstimateFrequencyA.</span><span class="sxs-lookup"><span data-stu-id="70d07-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="70d07-106">A EstimateFrequencyA beépített emulációs funkcióval rendelkezik a QuantumSimulator célzásához, ami felgyorsítja a végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="70d07-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="70d07-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="70d07-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="70d07-108">inputState: ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="70d07-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="70d07-109">A PrepareTrialState futtatásához szükséges Jordan-Wigner bemenet.</span><span class="sxs-lookup"><span data-stu-id="70d07-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="70d07-110">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="70d07-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="70d07-111">Egy qubit-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="70d07-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70d07-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70d07-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

