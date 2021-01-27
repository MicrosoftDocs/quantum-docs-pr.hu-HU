---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841682"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="b65db-102">ApplyMultiControlledCA művelet</span><span class="sxs-lookup"><span data-stu-id="b65db-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="b65db-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b65db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b65db-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b65db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b65db-105">Egy megfelelően vezérelt művelet szorzás vezérelt verzióját alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="b65db-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="b65db-106">A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="b65db-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b65db-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b65db-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="b65db-108">singlyControlledOp: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b65db-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b65db-109">Egyetlen qubit vezérelt művelet.</span><span class="sxs-lookup"><span data-stu-id="b65db-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="b65db-110">A művelet argumentumának első qubit a vezérlőnek kell lennie, és a többi a cél qubits feltételezhető.</span><span class="sxs-lookup"><span data-stu-id="b65db-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="b65db-111">`ApplyMultiControlled` mindig legalább 1 argumentummal hívja meg a metódust `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="b65db-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="b65db-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="b65db-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="b65db-113">A vezérelt vezérléssel nem rendelkező kapu, amely az építkezéshez használható.</span><span class="sxs-lookup"><span data-stu-id="b65db-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="b65db-114">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b65db-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b65db-115">A qubits `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="b65db-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="b65db-116">A hosszának `controls` legalább 1-nek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b65db-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="b65db-117">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b65db-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b65db-118">A megcélzott qubits `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="b65db-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b65db-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b65db-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b65db-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b65db-120">Remarks</span></span>

<span data-ttu-id="b65db-121">Ez a művelet csak a tiszta Ancilla-qubits használja.</span><span class="sxs-lookup"><span data-stu-id="b65db-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="b65db-122">A magyarázathoz és az áramköri diagramhoz lásd a 4,10., 4,3. szakaszát a Nielsen & a következő ábrán:</span><span class="sxs-lookup"><span data-stu-id="b65db-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="b65db-123">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="b65db-123">References</span></span>

- [<span data-ttu-id="b65db-124">*Michael A. Nielsen, Isaac L.*, a Quantum számítási és a kvantum-információk</span><span class="sxs-lookup"><span data-stu-id="b65db-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="b65db-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b65db-125">See Also</span></span>

- [<span data-ttu-id="b65db-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="b65db-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)