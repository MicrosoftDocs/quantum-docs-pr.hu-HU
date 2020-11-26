---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217747"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="17e71-102">ApplyToEachCA művelet</span><span class="sxs-lookup"><span data-stu-id="17e71-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="17e71-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17e71-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17e71-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17e71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17e71-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="17e71-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="17e71-106">A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="17e71-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="17e71-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="17e71-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="17e71-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="17e71-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="17e71-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="17e71-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="17e71-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="17e71-110">register : 'T[]</span></span>

<span data-ttu-id="17e71-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="17e71-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17e71-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17e71-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="17e71-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="17e71-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17e71-114">Nem</span><span class="sxs-lookup"><span data-stu-id="17e71-114">'T</span></span>

<span data-ttu-id="17e71-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="17e71-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="17e71-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="17e71-116">See Also</span></span>

- [<span data-ttu-id="17e71-117">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="17e71-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)