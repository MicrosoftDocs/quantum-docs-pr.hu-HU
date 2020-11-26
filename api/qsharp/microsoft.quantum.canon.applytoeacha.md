---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217798"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="93475-102">ApplyToEachA művelet</span><span class="sxs-lookup"><span data-stu-id="93475-102">ApplyToEachA operation</span></span>

<span data-ttu-id="93475-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93475-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93475-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93475-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93475-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="93475-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="93475-106">A módosító `A` azt jelzi, hogy az qubit művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="93475-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="93475-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="93475-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="93475-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93475-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="93475-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="93475-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="93475-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="93475-110">register : 'T[]</span></span>

<span data-ttu-id="93475-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="93475-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="93475-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93475-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93475-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="93475-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93475-114">Nem</span><span class="sxs-lookup"><span data-stu-id="93475-114">'T</span></span>

<span data-ttu-id="93475-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="93475-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="93475-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="93475-116">See Also</span></span>

- [<span data-ttu-id="93475-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="93475-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)