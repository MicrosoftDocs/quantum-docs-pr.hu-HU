---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9485c6549ed4e1a6fb3abdfa3f85ba35579d8b0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717575"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="f4afa-102">ApplyToEachA művelet</span><span class="sxs-lookup"><span data-stu-id="f4afa-102">ApplyToEachA operation</span></span>

<span data-ttu-id="f4afa-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4afa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4afa-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4afa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4afa-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="f4afa-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="f4afa-106">A módosító `A` azt jelzi, hogy az qubit művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="f4afa-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f4afa-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f4afa-107">Input</span></span>

### <a name="singleelementoperation--t--unit-adj"></a><span data-ttu-id="f4afa-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="f4afa-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f4afa-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="f4afa-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f4afa-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="f4afa-110">register : 'T[]</span></span>

<span data-ttu-id="f4afa-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="f4afa-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4afa-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4afa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4afa-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f4afa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4afa-114">Nem</span><span class="sxs-lookup"><span data-stu-id="f4afa-114">'T</span></span>

<span data-ttu-id="f4afa-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="f4afa-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4afa-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f4afa-116">See Also</span></span>

- [<span data-ttu-id="f4afa-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f4afa-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)