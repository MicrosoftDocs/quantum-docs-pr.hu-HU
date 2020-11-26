---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: PrepareSingleConfigurationalStateSingleSiteOccupation művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: 360800037318f56d0bb659aeb2a2c6292f860b2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214551"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a><span data-ttu-id="fdcf6-102">PrepareSingleConfigurationalStateSingleSiteOccupation művelet</span><span class="sxs-lookup"><span data-stu-id="fdcf6-102">PrepareSingleConfigurationalStateSingleSiteOccupation operation</span></span>

<span data-ttu-id="fdcf6-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fdcf6-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fdcf6-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fdcf6-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fdcf6-105">Próbaverziós állapot egyszerű állapotának előkészítése a spin-orbits elfoglalásával</span><span class="sxs-lookup"><span data-stu-id="fdcf6-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fdcf6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fdcf6-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="fdcf6-107">qubitIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fdcf6-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fdcf6-108">Az elektronok által foglalt qubits indexek.</span><span class="sxs-lookup"><span data-stu-id="fdcf6-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fdcf6-109">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fdcf6-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fdcf6-110">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="fdcf6-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fdcf6-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdcf6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

