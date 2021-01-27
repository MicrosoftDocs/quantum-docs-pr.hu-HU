---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: be820c87ee19230713d6c3e5681bbe3678040e95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850469"
---
# <a name="applytosubregister-operation"></a><span data-ttu-id="61e44-102">ApplyToSubregister művelet</span><span class="sxs-lookup"><span data-stu-id="61e44-102">ApplyToSubregister operation</span></span>

<span data-ttu-id="61e44-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61e44-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61e44-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61e44-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61e44-105">Egy műveletet alkalmaz egy regiszter alnyilvántartásába, és az qubits egy tömb adja meg.</span><span class="sxs-lookup"><span data-stu-id="61e44-105">Applies an operation to a subregister of a register, with qubits specified by an array of their indices.</span></span>

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="61e44-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="61e44-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="61e44-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61e44-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="61e44-108">A alregisztrációra alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="61e44-108">Operation to apply to subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="61e44-109">idxs: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="61e44-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="61e44-110">Indexek tömbje, amely azt jelzi, hogy a művelet mely qubits lesz alkalmazva.</span><span class="sxs-lookup"><span data-stu-id="61e44-110">Array of indices, indicating to which qubits the operation will be applied.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="61e44-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="61e44-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="61e44-112">Regisztrálja, hogy a művelet milyen műveleteket végez.</span><span class="sxs-lookup"><span data-stu-id="61e44-112">Register on which the operation acts.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61e44-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61e44-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="61e44-114">Példa</span><span class="sxs-lookup"><span data-stu-id="61e44-114">Example</span></span>

<span data-ttu-id="61e44-115">Hozzon létre három qubit állapotot $ \frac {1} {\sqrt {2} } \ket {0} \_ 2 (\ket {0} \_ 1 \ ket {0} _3 + \ket {1} \_ 1 \ ket {1} _3) $:</span><span class="sxs-lookup"><span data-stu-id="61e44-115">Create three qubit state $\frac{1}{\sqrt{2}}\ket{0}\_2(\ket{0}\_1\ket{0}_3+\ket{1}\_1\ket{1}_3)$:</span></span>

```qsharp
    using (register = Qubit[3]) {
        ApplyToSubregister(Exp([PauliX,PauliY],PI() / 4.0,_), [1,3], register);
    }
```

## <a name="see-also"></a><span data-ttu-id="61e44-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="61e44-116">See Also</span></span>

- [<span data-ttu-id="61e44-117">Microsoft. Quantum. Canon. ApplyToSubregisterA</span><span class="sxs-lookup"><span data-stu-id="61e44-117">Microsoft.Quantum.Canon.ApplyToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [<span data-ttu-id="61e44-118">Microsoft. Quantum. Canon. ApplyToSubregisterC</span><span class="sxs-lookup"><span data-stu-id="61e44-118">Microsoft.Quantum.Canon.ApplyToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [<span data-ttu-id="61e44-119">Microsoft. Quantum. Canon. ApplyToSubregisterCA</span><span class="sxs-lookup"><span data-stu-id="61e44-119">Microsoft.Quantum.Canon.ApplyToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)