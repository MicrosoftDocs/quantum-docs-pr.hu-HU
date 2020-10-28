---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721228"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="6fff2-102">ComputeReciprocalI művelet</span><span class="sxs-lookup"><span data-stu-id="6fff2-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="6fff2-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6fff2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6fff2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fff2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fff2-105">Kiszámítja az 1/x értéket egy előjel nélküli egész x-re az egész szám osztással.</span><span class="sxs-lookup"><span data-stu-id="6fff2-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="6fff2-106">Az eredmény az egész számként értelmezve lesz `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="6fff2-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="6fff2-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6fff2-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="6fff2-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6fff2-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6fff2-109">n bites előjel nélküli egész szám</span><span class="sxs-lookup"><span data-stu-id="6fff2-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="6fff2-110">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6fff2-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6fff2-111">a 2n-bites kimenetnek kezdetben $ \ket $ értékűnek kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="6fff2-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fff2-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fff2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6fff2-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6fff2-113">Remarks</span></span>

<span data-ttu-id="6fff2-114">Az x = 0 bemenet esetén a kimenet minden esetben megjelenik.</span><span class="sxs-lookup"><span data-stu-id="6fff2-114">For the input x=0, the output will be all-ones.</span></span>