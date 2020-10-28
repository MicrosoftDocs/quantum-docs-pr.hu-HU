---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: b24fbb8c7a1a55c0a7750c5d096a61f4824dadfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717547"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="94b18-102">ApplyToEachCA művelet</span><span class="sxs-lookup"><span data-stu-id="94b18-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="94b18-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94b18-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94b18-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94b18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94b18-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="94b18-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="94b18-106">A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="94b18-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="94b18-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="94b18-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj--ctl"></a><span data-ttu-id="94b18-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="94b18-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="94b18-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="94b18-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="94b18-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="94b18-110">register : 'T[]</span></span>

<span data-ttu-id="94b18-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="94b18-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94b18-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94b18-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94b18-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="94b18-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94b18-114">Nem</span><span class="sxs-lookup"><span data-stu-id="94b18-114">'T</span></span>

<span data-ttu-id="94b18-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="94b18-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="94b18-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="94b18-116">See Also</span></span>

- [<span data-ttu-id="94b18-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="94b18-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)