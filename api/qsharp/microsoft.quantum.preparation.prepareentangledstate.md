---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722171"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="e9520-102">PrepareEntangledState művelet</span><span class="sxs-lookup"><span data-stu-id="e9520-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="e9520-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e9520-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e9520-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9520-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9520-105">A páros két qubit-regisztrációt is összekever.</span><span class="sxs-lookup"><span data-stu-id="e9520-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="e9520-106">Ez azt eredményezi, hogy a két regisztráció során a rendszer előkészíti a maximálisan összefoglalt állapotot ($ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) a megfelelő regisztereken található egyes qubits között, feltételezve, hogy minden egyes regisztráció a $ \ket{0\cdots 0} $ állapottal kezdődik.</span><span class="sxs-lookup"><span data-stu-id="e9520-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e9520-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e9520-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="e9520-108">balra: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9520-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9520-109">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="e9520-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="e9520-110">jobb: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9520-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9520-111">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="e9520-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9520-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9520-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

