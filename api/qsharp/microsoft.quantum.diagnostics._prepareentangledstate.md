---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 5a74978a536a92dafae0b532805bd8e8ae1c888e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830972"
---
# <a name="_prepareentangledstate-operation"></a><span data-ttu-id="603fc-102">_prepareEntangledState művelet</span><span class="sxs-lookup"><span data-stu-id="603fc-102">_prepareEntangledState operation</span></span>

<span data-ttu-id="603fc-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="603fc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="603fc-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="603fc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="603fc-105">A két regisztráció során a rendszer előkészíti a maximálisan kusza állapotot a megfelelő regisztereken található egyes qubits között.</span><span class="sxs-lookup"><span data-stu-id="603fc-105">Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers.</span></span>
<span data-ttu-id="603fc-106">Minden qubits a (z) | 0 ⟩ állapotban kell kezdődnie.</span><span class="sxs-lookup"><span data-stu-id="603fc-106">All qubits must start in the |0⟩ state.</span></span>

<span data-ttu-id="603fc-107">Ennek eredményeképpen az egyes regisztrációk qubits tartozó párok a $ \bra{\ beta_ {00} } \ket{\ beta_} $ értékben találhatók {00} .</span><span class="sxs-lookup"><span data-stu-id="603fc-107">The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.</span></span>

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="603fc-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="603fc-108">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="603fc-109">balra: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="603fc-109">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="603fc-110">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="603fc-110">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="603fc-111">jobb: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="603fc-111">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="603fc-112">Qubit tömb a $ \ket{0\cdots 0} $ állapotban</span><span class="sxs-lookup"><span data-stu-id="603fc-112">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="603fc-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="603fc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

