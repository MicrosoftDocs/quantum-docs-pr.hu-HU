---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844621"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="9c39f-102">ApplyToEach művelet</span><span class="sxs-lookup"><span data-stu-id="9c39f-102">ApplyToEach operation</span></span>

<span data-ttu-id="9c39f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c39f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c39f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c39f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c39f-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.</span><span class="sxs-lookup"><span data-stu-id="9c39f-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9c39f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9c39f-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="9c39f-107">singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c39f-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9c39f-108">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="9c39f-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9c39f-109">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="9c39f-109">register : 'T[]</span></span>

<span data-ttu-id="9c39f-110">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="9c39f-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c39f-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c39f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c39f-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9c39f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c39f-113">Nem</span><span class="sxs-lookup"><span data-stu-id="9c39f-113">'T</span></span>

<span data-ttu-id="9c39f-114">Az a cél, amelyen a művelet működik.</span><span class="sxs-lookup"><span data-stu-id="9c39f-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="9c39f-115">Példa</span><span class="sxs-lookup"><span data-stu-id="9c39f-115">Example</span></span>

<span data-ttu-id="9c39f-116">Készítse elő a három qubit $ \ket{+} $ állapotot:</span><span class="sxs-lookup"><span data-stu-id="9c39f-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="9c39f-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9c39f-117">See Also</span></span>

- [<span data-ttu-id="9c39f-118">Microsoft. Quantum. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="9c39f-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="9c39f-119">Microsoft. Quantum. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="9c39f-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="9c39f-120">Microsoft. Quantum. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="9c39f-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)