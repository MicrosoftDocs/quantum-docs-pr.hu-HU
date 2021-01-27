---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850809"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="8490b-102">ApplyToEachIndexC művelet</span><span class="sxs-lookup"><span data-stu-id="8490b-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="8490b-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8490b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8490b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8490b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8490b-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="8490b-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="8490b-106">A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="8490b-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="8490b-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8490b-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="8490b-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="8490b-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8490b-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="8490b-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="8490b-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="8490b-110">register : 'T[]</span></span>

<span data-ttu-id="8490b-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="8490b-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8490b-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8490b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8490b-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8490b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8490b-114">Nem</span><span class="sxs-lookup"><span data-stu-id="8490b-114">'T</span></span>

<span data-ttu-id="8490b-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="8490b-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="8490b-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8490b-116">See Also</span></span>

- [<span data-ttu-id="8490b-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="8490b-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)