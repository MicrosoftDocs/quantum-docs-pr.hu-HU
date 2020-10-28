---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713136"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="010bd-102">_prepareEntangledState művelet</span><span class="sxs-lookup"><span data-stu-id="010bd-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="010bd-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="010bd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="010bd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="010bd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="010bd-105">A két regisztráció során a rendszer előkészíti a maximálisan kusza állapotot a megfelelő regisztereken található egyes qubits között.</span><span class="sxs-lookup"><span data-stu-id="010bd-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="010bd-106">Minden qubits a (z) | 0 ⟩ állapotban kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="010bd-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="010bd-107">Ennek eredményeképpen az egyes regisztrációk qubits tartozó párok a $ \bra{\ beta_ {00} } \ket{\ beta_} $ értékben találhatók {00} .</span><span class="sxs-lookup"><span data-stu-id="010bd-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="010bd-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="010bd-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="010bd-109">balra: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="010bd-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="010bd-110">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="010bd-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="010bd-111">jobb: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="010bd-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="010bd-112">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="010bd-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="010bd-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="010bd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

