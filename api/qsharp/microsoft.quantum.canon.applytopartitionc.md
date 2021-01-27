---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 43cf43fa2bf9c00a4096b39555b8f6080dd506d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850529"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="2f7ab-102">ApplyToPartitionC művelet</span><span class="sxs-lookup"><span data-stu-id="2f7ab-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="2f7ab-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f7ab-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f7ab-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f7ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f7ab-105">Egy pár műveletet alkalmaz a regiszter egy adott partícióján két részre.</span><span class="sxs-lookup"><span data-stu-id="2f7ab-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="2f7ab-106">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="2f7ab-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2f7ab-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2f7ab-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="2f7ab-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2f7ab-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2f7ab-109">Az adott partíción alkalmazni kívánt műveletek pár.</span><span class="sxs-lookup"><span data-stu-id="2f7ab-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="2f7ab-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f7ab-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f7ab-111">Azon qubits száma, amelyeket a rendszer a partíció első részébe helyez.</span><span class="sxs-lookup"><span data-stu-id="2f7ab-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="2f7ab-112">A fennmaradó qubits a partíció második részét képezik.</span><span class="sxs-lookup"><span data-stu-id="2f7ab-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2f7ab-113">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2f7ab-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2f7ab-114">A megadott két művelet által particionált és üzemeltetett qubits-jegyzék.</span><span class="sxs-lookup"><span data-stu-id="2f7ab-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f7ab-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f7ab-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2f7ab-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2f7ab-116">See Also</span></span>

- [<span data-ttu-id="2f7ab-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="2f7ab-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)