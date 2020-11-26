---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217781"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="bc677-102">ApplyToEachC művelet</span><span class="sxs-lookup"><span data-stu-id="bc677-102">ApplyToEachC operation</span></span>

<span data-ttu-id="bc677-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc677-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc677-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc677-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc677-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="bc677-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="bc677-106">A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="bc677-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="bc677-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc677-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="bc677-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="bc677-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="bc677-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="bc677-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bc677-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="bc677-110">register : 'T[]</span></span>

<span data-ttu-id="bc677-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="bc677-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc677-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc677-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc677-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bc677-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc677-114">Nem</span><span class="sxs-lookup"><span data-stu-id="bc677-114">'T</span></span>

<span data-ttu-id="bc677-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="bc677-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc677-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bc677-116">See Also</span></span>

- [<span data-ttu-id="bc677-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="bc677-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)