---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717113"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="5ed78-102">ApplyToPartitionC művelet</span><span class="sxs-lookup"><span data-stu-id="5ed78-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="5ed78-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ed78-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ed78-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ed78-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ed78-105">Egy pár műveletet alkalmaz a regiszter egy adott partícióján két részre.</span><span class="sxs-lookup"><span data-stu-id="5ed78-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="5ed78-106">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="5ed78-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5ed78-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5ed78-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="5ed78-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="5ed78-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5ed78-109">Az adott partíción alkalmazni kívánt műveletek pár.</span><span class="sxs-lookup"><span data-stu-id="5ed78-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="5ed78-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ed78-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ed78-111">Azon qubits száma, amelyeket a rendszer a partíció első részébe helyez.</span><span class="sxs-lookup"><span data-stu-id="5ed78-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="5ed78-112">A fennmaradó qubits a partíció második részét képezik.</span><span class="sxs-lookup"><span data-stu-id="5ed78-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5ed78-113">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5ed78-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5ed78-114">A megadott két művelet által particionált és üzemeltetett qubits-jegyzék.</span><span class="sxs-lookup"><span data-stu-id="5ed78-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ed78-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ed78-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5ed78-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="5ed78-116">See Also</span></span>

- [<span data-ttu-id="5ed78-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="5ed78-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)