---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846722"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="9eaf5-102">ComputeReciprocalI művelet</span><span class="sxs-lookup"><span data-stu-id="9eaf5-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="9eaf5-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9eaf5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9eaf5-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9eaf5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9eaf5-105">Kiszámítja az 1/x értéket egy előjel nélküli egész x-re az egész szám osztással.</span><span class="sxs-lookup"><span data-stu-id="9eaf5-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="9eaf5-106">Az eredmény az egész számként értelmezve lesz `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="9eaf5-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9eaf5-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9eaf5-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="9eaf5-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9eaf5-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9eaf5-109">n bites előjel nélküli egész szám</span><span class="sxs-lookup"><span data-stu-id="9eaf5-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="9eaf5-110">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9eaf5-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9eaf5-111">a 2n-bites kimenetnek kezdetben $ \ket $ értékűnek kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="9eaf5-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9eaf5-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9eaf5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9eaf5-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9eaf5-113">Remarks</span></span>

<span data-ttu-id="9eaf5-114">Az x = 0 bemenet esetén a kimenet minden esetben megjelenik.</span><span class="sxs-lookup"><span data-stu-id="9eaf5-114">For the input x=0, the output will be all-ones.</span></span>