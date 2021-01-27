---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850830"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="569d5-102">ApplyToEachIndexA művelet</span><span class="sxs-lookup"><span data-stu-id="569d5-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="569d5-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="569d5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="569d5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="569d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="569d5-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="569d5-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="569d5-106">A módosító `A` azt jelzi, hogy az qubit művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="569d5-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="569d5-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="569d5-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="569d5-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="569d5-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="569d5-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="569d5-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="569d5-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="569d5-110">register : 'T[]</span></span>

<span data-ttu-id="569d5-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="569d5-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="569d5-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="569d5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="569d5-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="569d5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="569d5-114">Nem</span><span class="sxs-lookup"><span data-stu-id="569d5-114">'T</span></span>

<span data-ttu-id="569d5-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="569d5-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="569d5-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="569d5-116">See Also</span></span>

- [<span data-ttu-id="569d5-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="569d5-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)