---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217594"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="b5f81-102">ApplyToEachIndexA művelet</span><span class="sxs-lookup"><span data-stu-id="b5f81-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="b5f81-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5f81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5f81-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5f81-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5f81-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="b5f81-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="b5f81-106">A módosító `A` azt jelzi, hogy az qubit művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="b5f81-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b5f81-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b5f81-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="b5f81-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5f81-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b5f81-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="b5f81-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="b5f81-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="b5f81-110">register : 'T[]</span></span>

<span data-ttu-id="b5f81-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="b5f81-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b5f81-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5f81-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5f81-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b5f81-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5f81-114">Nem</span><span class="sxs-lookup"><span data-stu-id="b5f81-114">'T</span></span>

<span data-ttu-id="b5f81-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="b5f81-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5f81-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b5f81-116">See Also</span></span>

- [<span data-ttu-id="b5f81-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="b5f81-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)