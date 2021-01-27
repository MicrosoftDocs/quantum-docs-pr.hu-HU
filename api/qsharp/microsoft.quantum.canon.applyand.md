---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 39ffb9c598b6345c0d63c0c0d9705d84e101cc47
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845186"
---
# <a name="applyand-operation"></a><span data-ttu-id="c6ee8-102">ApplyAnd művelet</span><span class="sxs-lookup"><span data-stu-id="c6ee8-102">ApplyAnd operation</span></span>

<span data-ttu-id="c6ee8-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6ee8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c6ee8-105">A megadott qubit csak akkor áll le, ha mindkét vezérlő qubits 1 állapotban van, a adjoint művelet végrehajtásához használja a mérést.</span><span class="sxs-lookup"><span data-stu-id="c6ee8-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c6ee8-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="c6ee8-106">Description</span></span>

<span data-ttu-id="c6ee8-107">`target`A csak akkor áll le, ha mindkét vezérlő 1, de feltételezi, hogy `target` a 0 állapotban van.</span><span class="sxs-lookup"><span data-stu-id="c6ee8-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="c6ee8-108">A műveletnek T-Count 4, T-depth 2, és nem igényel segítő qubit, és ezért előnyös lehet egy CCNOT művelethez, ha `target` az ismert értéke 0.</span><span class="sxs-lookup"><span data-stu-id="c6ee8-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="c6ee8-109">A művelet adjoint a mérésen alapul, és nem igényel T-kapukat.</span><span class="sxs-lookup"><span data-stu-id="c6ee8-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="c6ee8-110">A művelet vezérelt alkalmazásához nem szükséges a segítő qubit, a `2^c` `Rz` Gates és a nem állítható mélységre, ahol `c` a a művelethez tartozó két vezérlőelemet tartalmazó általános qubits száma `ApplyAnd` .</span><span class="sxs-lookup"><span data-stu-id="c6ee8-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="c6ee8-111">A adjoint által vezérelt alkalmazáshoz `2^c - 1` `Rz` kapuk szükségesek (a nem adjoint művelet méretének kétszerese), a segítő qubit nem, és nincs mélységre optimalizálva.</span><span class="sxs-lookup"><span data-stu-id="c6ee8-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="c6ee8-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c6ee8-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="c6ee8-113">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6ee8-114">Első vezérlő qubit</span><span class="sxs-lookup"><span data-stu-id="c6ee8-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="c6ee8-115">2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6ee8-116">Második vezérlő qubit</span><span class="sxs-lookup"><span data-stu-id="c6ee8-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c6ee8-117">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c6ee8-118">Cél kiegészítő qubit; a kötelező állapot 0</span><span class="sxs-lookup"><span data-stu-id="c6ee8-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6ee8-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="c6ee8-120">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="c6ee8-120">References</span></span>

- <span data-ttu-id="c6ee8-121">Cody Jones: "új konstrukciók a hibatűrő Toffoli kapuhoz", leltár. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="c6ee8-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="c6ee8-122">Craig Gidney: "a kvantum-Hozzáadás díja", Quantum 2, oldal 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) Doi: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="c6ee8-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="c6ee8-123">Mathias Soeken: "Quantum Oracle-áramkörök és a karácsonyfa mintája", [blog december 19., 2019](https://msoeken.github.io/blog_qac.html) (Megjegyzés: a több vezérelt szerkezet ismertetése)</span><span class="sxs-lookup"><span data-stu-id="c6ee8-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>