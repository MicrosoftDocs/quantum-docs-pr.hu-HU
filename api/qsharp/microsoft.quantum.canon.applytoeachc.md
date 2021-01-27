---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850855"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="3cede-102">ApplyToEachC művelet</span><span class="sxs-lookup"><span data-stu-id="3cede-102">ApplyToEachC operation</span></span>

<span data-ttu-id="3cede-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3cede-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3cede-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3cede-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3cede-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="3cede-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="3cede-106">A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="3cede-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="3cede-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3cede-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="3cede-108">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="3cede-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3cede-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="3cede-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="3cede-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="3cede-110">register : 'T[]</span></span>

<span data-ttu-id="3cede-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="3cede-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3cede-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3cede-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3cede-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3cede-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3cede-114">Nem</span><span class="sxs-lookup"><span data-stu-id="3cede-114">'T</span></span>

<span data-ttu-id="3cede-115">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="3cede-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="3cede-116">Példa</span><span class="sxs-lookup"><span data-stu-id="3cede-116">Example</span></span>

<span data-ttu-id="3cede-117">Készítse elő a három qubit $ \ket{+} $ állapotot:</span><span class="sxs-lookup"><span data-stu-id="3cede-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="3cede-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3cede-118">See Also</span></span>

- [<span data-ttu-id="3cede-119">Microsoft. Quantum. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="3cede-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)