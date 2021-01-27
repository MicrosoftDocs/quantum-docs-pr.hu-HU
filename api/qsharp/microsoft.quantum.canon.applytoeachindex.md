---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: ApplyToEachIndex művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844589"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="39e60-102">ApplyToEachIndex művelet</span><span class="sxs-lookup"><span data-stu-id="39e60-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="39e60-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39e60-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39e60-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39e60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39e60-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="39e60-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="39e60-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="39e60-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="39e60-107">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39e60-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="39e60-108">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="39e60-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="39e60-109">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="39e60-109">register : 'T[]</span></span>

<span data-ttu-id="39e60-110">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="39e60-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39e60-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39e60-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="39e60-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="39e60-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39e60-113">Nem</span><span class="sxs-lookup"><span data-stu-id="39e60-113">'T</span></span>

<span data-ttu-id="39e60-114">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="39e60-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="39e60-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="39e60-115">See Also</span></span>

- [<span data-ttu-id="39e60-116">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="39e60-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="39e60-117">Microsoft. Quantum. Canon. ApplyToEachIndexA</span><span class="sxs-lookup"><span data-stu-id="39e60-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="39e60-118">Microsoft. Quantum. Canon. ApplyToEachIndexC</span><span class="sxs-lookup"><span data-stu-id="39e60-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="39e60-119">Microsoft. Quantum. Canon. ApplyToEachIndexCA</span><span class="sxs-lookup"><span data-stu-id="39e60-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)