---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717518"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="22936-102">ApplyToEachIndexCA művelet</span><span class="sxs-lookup"><span data-stu-id="22936-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="22936-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="22936-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="22936-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22936-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22936-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="22936-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="22936-106">A módosító `CA` azt jelzi, hogy az qubit művelet adjointable és ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="22936-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="22936-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="22936-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="22936-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="22936-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="22936-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="22936-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="22936-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="22936-110">register : 'T[]</span></span>

<span data-ttu-id="22936-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="22936-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22936-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22936-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="22936-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="22936-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22936-114">Nem</span><span class="sxs-lookup"><span data-stu-id="22936-114">'T</span></span>

<span data-ttu-id="22936-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="22936-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="22936-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="22936-116">See Also</span></span>

- [<span data-ttu-id="22936-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="22936-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)