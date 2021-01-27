---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: fa19c3bb06ae91a2fa18acb6f853020830e749f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847235"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="2fd74-102">ApplyFixedPointAmplification művelet</span><span class="sxs-lookup"><span data-stu-id="2fd74-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="2fd74-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2fd74-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2fd74-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2fd74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2fd74-105">Fixed-Point amplitúdó-erősítési algoritmus</span><span class="sxs-lookup"><span data-stu-id="2fd74-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2fd74-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2fd74-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="2fd74-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="2fd74-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="2fd74-108">Az egységes Oracle, amely előkészíti a kezdő állapotot.</span><span class="sxs-lookup"><span data-stu-id="2fd74-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="2fd74-109">startQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2fd74-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2fd74-110">Qubit-regisztráció</span><span class="sxs-lookup"><span data-stu-id="2fd74-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fd74-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fd74-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fd74-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2fd74-112">Remarks</span></span>

<span data-ttu-id="2fd74-113">A startQubits a $ \ket{0 \cdots 0} $ állapotban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="2fd74-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="2fd74-114">Ez a művelet több, $2 $ értékű lekérdezésre mutat be, amíg el nem éri a lekérdezések maximális számát, vagy megtalálhatók a célként megadott állapot.</span><span class="sxs-lookup"><span data-stu-id="2fd74-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>