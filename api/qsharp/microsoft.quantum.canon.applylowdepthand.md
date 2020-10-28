---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 092a350e42d8d90942de13530fefd761b5187e1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717981"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="d1ee6-102">ApplyLowDepthAnd művelet</span><span class="sxs-lookup"><span data-stu-id="d1ee6-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="d1ee6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1ee6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1ee6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1ee6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d1ee6-105">A megadott qubit csak akkor áll le, ha mindkét vezérlő qubits 1 állapotban van, a T-depth 1 értékkel, a adjoint művelet elvégzéséhez használja a mérést.</span><span class="sxs-lookup"><span data-stu-id="d1ee6-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="d1ee6-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d1ee6-106">Description</span></span>

<span data-ttu-id="d1ee6-107">`target`A csak akkor áll le, ha mindkét vezérlő 1, de feltételezi, hogy `target` a 0 állapotban van.</span><span class="sxs-lookup"><span data-stu-id="d1ee6-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="d1ee6-108">A műveletnek T-Count 4, T-depth 1, és egy segítő qubit van szüksége, ezért érdemes lehet egy CCNOT-műveletnek lennie, ha `target` az ismert értéke 0.</span><span class="sxs-lookup"><span data-stu-id="d1ee6-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="d1ee6-109">A művelet adjoint a mérésen alapul, és nem igényel T-kaput, és nincs segítő qubit.</span><span class="sxs-lookup"><span data-stu-id="d1ee6-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="d1ee6-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d1ee6-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="d1ee6-111">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1ee6-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1ee6-112">Első vezérlő qubit</span><span class="sxs-lookup"><span data-stu-id="d1ee6-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="d1ee6-113">2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1ee6-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1ee6-114">Második vezérlő qubit</span><span class="sxs-lookup"><span data-stu-id="d1ee6-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d1ee6-115">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1ee6-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1ee6-116">Cél kiegészítő qubit; a kötelező állapot 0</span><span class="sxs-lookup"><span data-stu-id="d1ee6-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1ee6-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1ee6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d1ee6-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="d1ee6-118">References</span></span>

- <span data-ttu-id="d1ee6-119">Cody Jones: "új konstrukciók a hibatűrő Toffoli kapuhoz", leltár. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="d1ee6-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="d1ee6-120">Peter Selinger: "T-depthal One", leltár. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) Doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="d1ee6-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>