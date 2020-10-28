---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713766"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="188d2-102">_prepareTrialStateWrapper művelet</span><span class="sxs-lookup"><span data-stu-id="188d2-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="188d2-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="188d2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="188d2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="188d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="188d2-105">A PrepareTrialState körüli privát burkoló egy adjoint definiálásával teszi kompatibilisvé a EstimateFrequencyA.</span><span class="sxs-lookup"><span data-stu-id="188d2-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="188d2-106">A EstimateFrequencyA beépített emulációs funkcióval rendelkezik a QuantumSimulator célzásához, ami felgyorsítja a végrehajtást.</span><span class="sxs-lookup"><span data-stu-id="188d2-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="188d2-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="188d2-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="188d2-108">inputState: ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="188d2-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="188d2-109">A PrepareTrialState futtatásához szükséges Jordan-Wigner bemenet.</span><span class="sxs-lookup"><span data-stu-id="188d2-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="188d2-110">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="188d2-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="188d2-111">Egy qubit-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="188d2-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="188d2-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="188d2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

