---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718457"
---
# <a name="applyand-operation"></a><span data-ttu-id="2b396-102">ApplyAnd művelet</span><span class="sxs-lookup"><span data-stu-id="2b396-102">ApplyAnd operation</span></span>

<span data-ttu-id="2b396-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b396-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b396-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b396-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b396-105">A megadott qubit csak akkor áll le, ha mindkét vezérlő qubits 1 állapotban van, a adjoint művelet végrehajtásához használja a mérést.</span><span class="sxs-lookup"><span data-stu-id="2b396-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="2b396-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="2b396-106">Description</span></span>

<span data-ttu-id="2b396-107">`target`A csak akkor áll le, ha mindkét vezérlő 1, de feltételezi, hogy `target` a 0 állapotban van.</span><span class="sxs-lookup"><span data-stu-id="2b396-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="2b396-108">A műveletnek T-Count 4, T-depth 2, és nem igényel segítő qubit, és ezért előnyös lehet egy CCNOT művelethez, ha `target` az ismert értéke 0.</span><span class="sxs-lookup"><span data-stu-id="2b396-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="2b396-109">A művelet adjoint a mérésen alapul, és nem igényel T-kapukat.</span><span class="sxs-lookup"><span data-stu-id="2b396-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="2b396-110">A művelet vezérelt alkalmazásához nem szükséges a segítő qubit, a `2^c` `Rz` Gates és a nem állítható mélységre, ahol `c` a a művelethez tartozó két vezérlőelemet tartalmazó általános qubits száma `ApplyAnd` .</span><span class="sxs-lookup"><span data-stu-id="2b396-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="2b396-111">A adjoint által vezérelt alkalmazáshoz `2^c - 1` `Rz` kapuk szükségesek (a nem adjoint művelet méretének kétszerese), a segítő qubit nem, és nincs mélységre optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="2b396-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="2b396-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2b396-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="2b396-113">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2b396-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2b396-114">Első vezérlő qubit</span><span class="sxs-lookup"><span data-stu-id="2b396-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="2b396-115">2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2b396-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2b396-116">Második vezérlő qubit</span><span class="sxs-lookup"><span data-stu-id="2b396-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2b396-117">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2b396-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2b396-118">Cél kiegészítő qubit; a kötelező állapot 0</span><span class="sxs-lookup"><span data-stu-id="2b396-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b396-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b396-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2b396-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="2b396-120">References</span></span>

- <span data-ttu-id="2b396-121">Cody Jones: "új konstrukciók a hibatűrő Toffoli kapuhoz", leltár. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="2b396-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="2b396-122">Craig Gidney: "a kvantum-Hozzáadás díja", Quantum 2, oldal 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) Doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="2b396-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="2b396-123">Mathias Soeken: "Quantum Oracle-áramkörök és a karácsonyfa mintája", [blog december 19., 2019](https://msoeken.github.io/blog_qac.html) (Megjegyzés: a több vezérelt szerkezet ismertetése)</span><span class="sxs-lookup"><span data-stu-id="2b396-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>