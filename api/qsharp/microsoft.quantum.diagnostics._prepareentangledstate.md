---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 97a55b4bb85095c7d8e8432dfcd1c6d6f7e93cdc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223935"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="20d2a-102">_prepareEntangledState művelet</span><span class="sxs-lookup"><span data-stu-id="20d2a-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="20d2a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="20d2a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="20d2a-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="20d2a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="20d2a-105">A két regisztráció során a rendszer előkészíti a maximálisan kusza állapotot a megfelelő regisztereken található egyes qubits között.</span><span class="sxs-lookup"><span data-stu-id="20d2a-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="20d2a-106">Minden qubits a (z) | 0 ⟩ állapotban kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="20d2a-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="20d2a-107">Ennek eredményeképpen az egyes regisztrációk qubits tartozó párok a $ \bra{\ beta_ {00} } \ket{\ beta_} $ értékben találhatók {00} .</span><span class="sxs-lookup"><span data-stu-id="20d2a-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="20d2a-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="20d2a-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="20d2a-109">balra: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="20d2a-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="20d2a-110">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="20d2a-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="20d2a-111">jobb: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="20d2a-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="20d2a-112">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="20d2a-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="20d2a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20d2a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

