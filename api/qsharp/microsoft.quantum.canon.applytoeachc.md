---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717561"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="91d28-102">ApplyToEachC művelet</span><span class="sxs-lookup"><span data-stu-id="91d28-102">ApplyToEachC operation</span></span>

<span data-ttu-id="91d28-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91d28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91d28-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91d28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91d28-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="91d28-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="91d28-106">A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="91d28-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="91d28-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="91d28-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="91d28-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="91d28-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="91d28-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="91d28-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="91d28-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="91d28-110">register : 'T[]</span></span>

<span data-ttu-id="91d28-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="91d28-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91d28-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91d28-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="91d28-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="91d28-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91d28-114">Nem</span><span class="sxs-lookup"><span data-stu-id="91d28-114">'T</span></span>

<span data-ttu-id="91d28-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="91d28-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="91d28-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="91d28-116">See Also</span></span>

- [<span data-ttu-id="91d28-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="91d28-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)