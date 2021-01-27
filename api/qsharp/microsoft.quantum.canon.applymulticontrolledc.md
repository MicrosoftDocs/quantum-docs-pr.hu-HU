---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844867"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="a6739-102">ApplyMultiControlledC művelet</span><span class="sxs-lookup"><span data-stu-id="a6739-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="a6739-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a6739-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a6739-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6739-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6739-105">Egy megfelelően vezérelt művelet szorzás vezérelt verzióját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="a6739-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="a6739-106">A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="a6739-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="a6739-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a6739-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="a6739-108">singlyControlledOp: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6739-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a6739-109">Egyetlen qubit vezérelt művelet.</span><span class="sxs-lookup"><span data-stu-id="a6739-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="a6739-110">A művelet argumentumának első qubit a vezérlőnek kell lennie, a többi pedig a célként megadott qubits.</span><span class="sxs-lookup"><span data-stu-id="a6739-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="a6739-111">`ApplyMultiControlled` mindig legalább 1 argumentummal hívja meg a metódust `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="a6739-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="a6739-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="a6739-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="a6739-113">A vezérelt vezérléssel nem rendelkező kapu, amely az építkezéshez használható.</span><span class="sxs-lookup"><span data-stu-id="a6739-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="a6739-114">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a6739-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a6739-115">A qubits `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="a6739-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="a6739-116">A hosszának `controls` legalább 1-nek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a6739-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="a6739-117">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a6739-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a6739-118">A megcélzott qubits `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="a6739-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a6739-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a6739-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a6739-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a6739-120">Remarks</span></span>

<span data-ttu-id="a6739-121">Ez a művelet csak a tiszta Ancilla-qubits használja.</span><span class="sxs-lookup"><span data-stu-id="a6739-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="a6739-122">A magyarázathoz és az áramköri diagramhoz lásd a 4,10., 4,3. szakaszát a Nielsen & a következő ábrán:</span><span class="sxs-lookup"><span data-stu-id="a6739-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="a6739-123">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="a6739-123">References</span></span>

- [<span data-ttu-id="a6739-124">*Michael A. Nielsen, Isaac L.*, a Quantum számítási és a kvantum-információk</span><span class="sxs-lookup"><span data-stu-id="a6739-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="a6739-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a6739-125">See Also</span></span>

- [<span data-ttu-id="a6739-126">Microsoft. Quantum. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="a6739-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)