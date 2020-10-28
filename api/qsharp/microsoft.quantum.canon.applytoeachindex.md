---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 4ce184b34add9238e26f9b35b40ec0bddb23ccf9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717546"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="384db-102">ApplyToEachIndex művelet</span><span class="sxs-lookup"><span data-stu-id="384db-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="384db-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="384db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="384db-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="384db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="384db-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="384db-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="384db-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="384db-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="384db-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="384db-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="384db-108">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="384db-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="384db-109">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="384db-109">register : 'T[]</span></span>

<span data-ttu-id="384db-110">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="384db-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="384db-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="384db-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="384db-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="384db-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="384db-113">Nem</span><span class="sxs-lookup"><span data-stu-id="384db-113">'T</span></span>

<span data-ttu-id="384db-114">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="384db-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="384db-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="384db-115">See Also</span></span>

- [<span data-ttu-id="384db-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="384db-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="384db-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="384db-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="384db-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="384db-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="384db-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="384db-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)