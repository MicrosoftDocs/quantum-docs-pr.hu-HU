---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: 9024da4a457265c65a41ef681cfbb99ebd4989a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223357"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="4f3a4-102">ComputeReciprocalI művelet</span><span class="sxs-lookup"><span data-stu-id="4f3a4-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="4f3a4-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4f3a4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4f3a4-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4f3a4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4f3a4-105">Kiszámítja az 1/x értéket egy előjel nélküli egész x-re az egész szám osztással.</span><span class="sxs-lookup"><span data-stu-id="4f3a4-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="4f3a4-106">Az eredmény az egész számként értelmezve lesz `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="4f3a4-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f3a4-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4f3a4-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4f3a4-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f3a4-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4f3a4-109">n bites előjel nélküli egész szám</span><span class="sxs-lookup"><span data-stu-id="4f3a4-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="4f3a4-110">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f3a4-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4f3a4-111">a 2n-bites kimenetnek kezdetben $ \ket $ értékűnek kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="4f3a4-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f3a4-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f3a4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4f3a4-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4f3a4-113">Remarks</span></span>

<span data-ttu-id="4f3a4-114">Az x = 0 bemenet esetén a kimenet minden esetben megjelenik.</span><span class="sxs-lookup"><span data-stu-id="4f3a4-114">For the input x=0, the output will be all-ones.</span></span>