---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209281"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="cb7f2-102">ApplyMultiControlledCA művelet</span><span class="sxs-lookup"><span data-stu-id="cb7f2-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="cb7f2-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb7f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb7f2-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb7f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb7f2-105">Egy megfelelően vezérelt művelet szorzás vezérelt verzióját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="cb7f2-106">A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cb7f2-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cb7f2-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="cb7f2-108">singlyControlledOp: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb7f2-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cb7f2-109">Egyetlen qubit vezérelt művelet.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="cb7f2-110">A művelet argumentumának első qubit a vezérlőnek kell lennie, és a többi a cél qubits feltételezhető.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="cb7f2-111">`ApplyMultiControlled` mindig legalább 1 argumentummal hívja meg a metódust `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="cb7f2-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="cb7f2-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="cb7f2-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="cb7f2-113">A vezérelt vezérléssel nem rendelkező kapu, amely az építkezéshez használható.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="cb7f2-114">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cb7f2-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cb7f2-115">A qubits `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="cb7f2-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="cb7f2-116">A hosszának `controls` legalább 1-nek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="cb7f2-117">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cb7f2-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cb7f2-118">A megcélzott qubits `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="cb7f2-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb7f2-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb7f2-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cb7f2-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cb7f2-120">Remarks</span></span>

<span data-ttu-id="cb7f2-121">Ez a művelet csak a tiszta Ancilla-qubits használja.</span><span class="sxs-lookup"><span data-stu-id="cb7f2-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="cb7f2-122">A magyarázathoz és az áramköri diagramhoz lásd a 4,10., 4,3. szakaszát a Nielsen & a következő ábrán:</span><span class="sxs-lookup"><span data-stu-id="cb7f2-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="cb7f2-123">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="cb7f2-123">References</span></span>

- [<span data-ttu-id="cb7f2-124">*Michael A. Nielsen, Isaac L.*, a Quantum számítási és a kvantum-információk</span><span class="sxs-lookup"><span data-stu-id="cb7f2-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="cb7f2-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="cb7f2-125">See Also</span></span>

- [<span data-ttu-id="cb7f2-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="cb7f2-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)