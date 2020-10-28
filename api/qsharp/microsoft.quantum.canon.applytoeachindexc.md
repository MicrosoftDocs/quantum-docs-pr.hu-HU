---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717532"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="299b0-102">ApplyToEachIndexC művelet</span><span class="sxs-lookup"><span data-stu-id="299b0-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="299b0-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="299b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="299b0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="299b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="299b0-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="299b0-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="299b0-106">A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="299b0-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="299b0-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="299b0-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-ctl"></a><span data-ttu-id="299b0-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="299b0-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="299b0-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="299b0-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="299b0-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="299b0-110">register : 'T[]</span></span>

<span data-ttu-id="299b0-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="299b0-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="299b0-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="299b0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="299b0-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="299b0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="299b0-114">Nem</span><span class="sxs-lookup"><span data-stu-id="299b0-114">'T</span></span>

<span data-ttu-id="299b0-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="299b0-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="299b0-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="299b0-116">See Also</span></span>

- [<span data-ttu-id="299b0-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="299b0-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)