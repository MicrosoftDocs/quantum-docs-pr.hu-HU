---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191533"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="65c47-102">ApplyFixedPointAmplification művelet</span><span class="sxs-lookup"><span data-stu-id="65c47-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="65c47-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="65c47-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="65c47-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65c47-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65c47-105">Fixed-Point amplitúdó-erősítési algoritmus</span><span class="sxs-lookup"><span data-stu-id="65c47-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="65c47-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="65c47-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="65c47-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="65c47-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="65c47-108">Az egységes Oracle, amely előkészíti a kezdő állapotot.</span><span class="sxs-lookup"><span data-stu-id="65c47-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="65c47-109">startQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="65c47-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="65c47-110">Qubit-regisztráció</span><span class="sxs-lookup"><span data-stu-id="65c47-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="65c47-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65c47-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="65c47-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="65c47-112">Remarks</span></span>

<span data-ttu-id="65c47-113">A startQubits a $ \ket{0 \cdots 0} $ állapotban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="65c47-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="65c47-114">Ez a művelet több, $2 $ értékű lekérdezésre mutat be, amíg el nem éri a lekérdezések maximális számát, vagy megtalálhatók a célként megadott állapot.</span><span class="sxs-lookup"><span data-stu-id="65c47-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>