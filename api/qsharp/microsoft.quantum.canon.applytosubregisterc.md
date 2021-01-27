---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterC
title: ApplyToSubregisterC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterC
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 52564e64d8cc9cdbeb2626ed8694168b8ed48c22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850463"
---
# <a name="applytosubregisterc-operation"></a><span data-ttu-id="05f1e-102">ApplyToSubregisterC művelet</span><span class="sxs-lookup"><span data-stu-id="05f1e-102">ApplyToSubregisterC operation</span></span>

<span data-ttu-id="05f1e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="05f1e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="05f1e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05f1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05f1e-105">Egy műveletet alkalmaz egy regiszter alnyilvántartásába, és az qubits egy tömb adja meg.</span><span class="sxs-lookup"><span data-stu-id="05f1e-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>
<span data-ttu-id="05f1e-106">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="05f1e-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[], target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="05f1e-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="05f1e-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="05f1e-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="05f1e-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="05f1e-109">A alregisztrációra alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="05f1e-109">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="05f1e-110">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="05f1e-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="05f1e-111">Indexek tömbje, amely azt jelzi, hogy a művelet mely qubits lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="05f1e-111">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="05f1e-112">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="05f1e-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="05f1e-113">Regisztrálja, hogy a művelet milyen műveleteket végez.</span><span class="sxs-lookup"><span data-stu-id="05f1e-113">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05f1e-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05f1e-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="05f1e-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="05f1e-115">See Also</span></span>

- [<span data-ttu-id="05f1e-116">Microsoft. Quantum. Canon. ApplyToSubregister</span><span class="sxs-lookup"><span data-stu-id="05f1e-116">Microsoft.Quantum.Canon.ApplyToSubregister</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregister)