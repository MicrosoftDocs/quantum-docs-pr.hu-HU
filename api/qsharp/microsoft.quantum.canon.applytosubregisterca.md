---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: ApplyToSubregisterCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716987"
---
# <a name="applytosubregisterca-operation"></a><span data-ttu-id="c6595-102">ApplyToSubregisterCA művelet</span><span class="sxs-lookup"><span data-stu-id="c6595-102">ApplyToSubregisterCA operation</span></span>

<span data-ttu-id="c6595-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6595-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6595-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6595-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6595-105">Egy műveletet alkalmaz egy regiszter alnyilvántartásába, és az qubits egy tömb adja meg.</span><span class="sxs-lookup"><span data-stu-id="c6595-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="c6595-106">A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="c6595-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c6595-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c6595-107">Input</span></span>

### <a name="op--qubit--unit-ctl--adj"></a><span data-ttu-id="c6595-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="c6595-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="c6595-109">A alregisztrációra alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="c6595-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="c6595-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c6595-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c6595-111">Indexek tömbje, amely azt jelzi, hogy a művelet mely qubits lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="c6595-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c6595-112">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c6595-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c6595-113">Regisztrálja, hogy a művelet milyen műveleteket végez.</span><span class="sxs-lookup"><span data-stu-id="c6595-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6595-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6595-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c6595-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c6595-115">See Also</span></span>

- [<span data-ttu-id="c6595-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="c6595-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)