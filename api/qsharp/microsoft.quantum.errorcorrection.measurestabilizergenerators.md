---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712268"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="eefb9-102">MeasureStabilizerGenerators művelet</span><span class="sxs-lookup"><span data-stu-id="eefb9-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="eefb9-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="eefb9-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="eefb9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eefb9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eefb9-105">A stabilizátorok csoportjának adott készletét méri.</span><span class="sxs-lookup"><span data-stu-id="eefb9-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="eefb9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eefb9-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="eefb9-107">stabilizerGroup: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="eefb9-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="eefb9-108">Multiqubit Pauli-operátorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="eefb9-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="eefb9-109">Például az egy `stabilizerGroup[0]` Qubit Pauli-mátrixok listája, amely a kétprocesszoros termék, amely egy stabilizátor generátor.</span><span class="sxs-lookup"><span data-stu-id="eefb9-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="eefb9-110">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="eefb9-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="eefb9-111">Olyan qubits tömbje, amelyben a stabilizátor kódja van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="eefb9-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="eefb9-112">Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="eefb9-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="eefb9-113">Egy multiqubit Pauli-operátor mérését megadó művelet.</span><span class="sxs-lookup"><span data-stu-id="eefb9-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="eefb9-114">Kimenet: [szindróma](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="eefb9-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="eefb9-115">A mérések eredménye.</span><span class="sxs-lookup"><span data-stu-id="eefb9-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="eefb9-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="eefb9-116">Remarks</span></span>

<span data-ttu-id="eefb9-117">Ezzel a beállítással nem ellenőrizhető, hogy az adott generátorok vannak-e ingázások.</span><span class="sxs-lookup"><span data-stu-id="eefb9-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="eefb9-118">Ha nem az ingázást végzik, lehetséges, hogy a mérések eredménye tetszőleges.</span><span class="sxs-lookup"><span data-stu-id="eefb9-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>