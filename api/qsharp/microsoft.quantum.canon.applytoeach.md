---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217866"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="d1ecd-102">ApplyToEach művelet</span><span class="sxs-lookup"><span data-stu-id="d1ecd-102">ApplyToEach operation</span></span>

<span data-ttu-id="d1ecd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d1ecd-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1ecd-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d1ecd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d1ecd-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="d1ecd-107">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d1ecd-108">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="d1ecd-109">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="d1ecd-109">register : 'T[]</span></span>

<span data-ttu-id="d1ecd-110">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1ecd-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1ecd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d1ecd-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d1ecd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1ecd-113">Nem</span><span class="sxs-lookup"><span data-stu-id="d1ecd-113">'T</span></span>

<span data-ttu-id="d1ecd-114">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="d1ecd-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1ecd-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d1ecd-115">See Also</span></span>

- [<span data-ttu-id="d1ecd-116">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="d1ecd-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="d1ecd-117">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="d1ecd-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="d1ecd-118">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="d1ecd-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)