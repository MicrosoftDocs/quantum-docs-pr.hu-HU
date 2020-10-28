---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: ApplyToPartitionA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 6ff3bf8b5a4344ee5a7a054c6285a5492260068d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717127"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="ab0ca-102">ApplyToPartitionA művelet</span><span class="sxs-lookup"><span data-stu-id="ab0ca-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="ab0ca-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab0ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab0ca-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab0ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab0ca-105">Egy pár műveletet alkalmaz a regiszter egy adott partícióján két részre.</span><span class="sxs-lookup"><span data-stu-id="ab0ca-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="ab0ca-106">A módosító `A` azt jelzi, hogy a művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="ab0ca-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ab0ca-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ab0ca-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj"></a><span data-ttu-id="ab0ca-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="ab0ca-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ab0ca-109">Az adott partíción alkalmazni kívánt műveletek pár.</span><span class="sxs-lookup"><span data-stu-id="ab0ca-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="ab0ca-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab0ca-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab0ca-111">Azon qubits száma, amelyeket a rendszer a partíció első részébe helyez.</span><span class="sxs-lookup"><span data-stu-id="ab0ca-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="ab0ca-112">A fennmaradó qubits a partíció második részét képezik.</span><span class="sxs-lookup"><span data-stu-id="ab0ca-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ab0ca-113">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ab0ca-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ab0ca-114">A megadott két művelet által particionált és üzemeltetett qubits-jegyzék.</span><span class="sxs-lookup"><span data-stu-id="ab0ca-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab0ca-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab0ca-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ab0ca-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ab0ca-116">See Also</span></span>

- [<span data-ttu-id="ab0ca-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="ab0ca-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)