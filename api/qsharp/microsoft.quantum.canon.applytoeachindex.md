---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 746bc19f7a137ef476a25abdabc4737ed6727ff2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217612"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="e47f6-102">ApplyToEachIndex művelet</span><span class="sxs-lookup"><span data-stu-id="e47f6-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="e47f6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e47f6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e47f6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e47f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e47f6-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="e47f6-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e47f6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e47f6-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="e47f6-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e47f6-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e47f6-108">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="e47f6-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="e47f6-109">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="e47f6-109">register : 'T[]</span></span>

<span data-ttu-id="e47f6-110">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="e47f6-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e47f6-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e47f6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e47f6-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e47f6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e47f6-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e47f6-113">'T</span></span>

<span data-ttu-id="e47f6-114">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="e47f6-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="e47f6-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e47f6-115">See Also</span></span>

- [<span data-ttu-id="e47f6-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="e47f6-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="e47f6-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="e47f6-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="e47f6-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="e47f6-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="e47f6-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="e47f6-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)