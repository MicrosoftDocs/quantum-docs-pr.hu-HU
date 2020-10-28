---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717029"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="2e0be-102">ApplyToSubregister művelet</span><span class="sxs-lookup"><span data-stu-id="2e0be-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="2e0be-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e0be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e0be-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e0be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e0be-105">Egy műveletet alkalmaz egy regiszter alnyilvántartásába, és az qubits egy tömb adja meg.</span><span class="sxs-lookup"><span data-stu-id="2e0be-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2e0be-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2e0be-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="2e0be-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e0be-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2e0be-108">A alregisztrációra alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="2e0be-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2e0be-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2e0be-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2e0be-110">Indexek tömbje, amely azt jelzi, hogy a művelet mely qubits lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="2e0be-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2e0be-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2e0be-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2e0be-112">Regisztrálja, hogy a művelet milyen műveleteket végez.</span><span class="sxs-lookup"><span data-stu-id="2e0be-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e0be-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e0be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2e0be-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2e0be-114">See Also</span></span>

- [<span data-ttu-id="2e0be-115">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="2e0be-115">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="2e0be-116">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="2e0be-116">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="2e0be-117">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="2e0be-117">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)