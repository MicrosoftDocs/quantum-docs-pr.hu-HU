---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: ApplyToEachIndexCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208941"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="63be8-102">ApplyToEachIndexCA művelet</span><span class="sxs-lookup"><span data-stu-id="63be8-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="63be8-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63be8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63be8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63be8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63be8-105">Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.</span><span class="sxs-lookup"><span data-stu-id="63be8-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="63be8-106">A módosító `CA` azt jelzi, hogy az qubit művelet adjointable és ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="63be8-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="63be8-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="63be8-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="63be8-108">singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="63be8-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="63be8-109">Az egyes qubit alkalmazandó művelet.</span><span class="sxs-lookup"><span data-stu-id="63be8-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="63be8-110">Regisztráció: 'T []</span><span class="sxs-lookup"><span data-stu-id="63be8-110">register : 'T[]</span></span>

<span data-ttu-id="63be8-111">Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.</span><span class="sxs-lookup"><span data-stu-id="63be8-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63be8-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63be8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63be8-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="63be8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63be8-114">Nem</span><span class="sxs-lookup"><span data-stu-id="63be8-114">'T</span></span>

<span data-ttu-id="63be8-115">A cél, amelyen az egyes műveletek működnek.</span><span class="sxs-lookup"><span data-stu-id="63be8-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="63be8-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="63be8-116">See Also</span></span>

- [<span data-ttu-id="63be8-117">Microsoft. Quantum. Canon. ApplyToEachIndex</span><span class="sxs-lookup"><span data-stu-id="63be8-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)