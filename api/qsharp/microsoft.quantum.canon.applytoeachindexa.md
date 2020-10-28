---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717533"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="8862c-102">ApplyToEachIndexA művelet</span><span class="sxs-lookup"><span data-stu-id="8862c-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="8862c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8862c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8862c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8862c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8862c-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="8862c-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="8862c-106">A módosító `A` azt jelzi, hogy az qubit művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="8862c-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8862c-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8862c-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="8862c-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="8862c-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="8862c-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="8862c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="8862c-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="8862c-110">register : 'T[]</span></span>

<span data-ttu-id="8862c-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="8862c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8862c-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8862c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8862c-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8862c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8862c-114">Nem</span><span class="sxs-lookup"><span data-stu-id="8862c-114">'T</span></span>

<span data-ttu-id="8862c-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="8862c-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="8862c-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8862c-116">See Also</span></span>

- [<span data-ttu-id="8862c-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="8862c-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)