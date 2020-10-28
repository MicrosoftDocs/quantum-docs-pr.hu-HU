---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721217"
---
# <a name="dividei-operation"></a><span data-ttu-id="60974-102">DivideI művelet</span><span class="sxs-lookup"><span data-stu-id="60974-102">DivideI operation</span></span>

<span data-ttu-id="60974-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="60974-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="60974-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60974-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60974-105">Két kvantum egész számot oszt ki.</span><span class="sxs-lookup"><span data-stu-id="60974-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="60974-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="60974-106">Description</span></span>

<span data-ttu-id="60974-107">`xs` a maradékot fogja tárolni `xs - floor(xs/ys) * ys` , és `result` megtartja `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="60974-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="60974-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="60974-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="60974-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="60974-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="60974-110">$n $-bit osztalékot, a fennmaradó összeg helyébe lép.</span><span class="sxs-lookup"><span data-stu-id="60974-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="60974-111">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="60974-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="60974-112">$n $ bites osztó</span><span class="sxs-lookup"><span data-stu-id="60974-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="60974-113">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="60974-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="60974-114">$n $-bit eredménynek kezdetben a $ \ket $ állapotban kell lennie, {0} és a rendszer az egész szám felosztásával váltja fel.</span><span class="sxs-lookup"><span data-stu-id="60974-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60974-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60974-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="60974-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="60974-116">Remarks</span></span>

<span data-ttu-id="60974-117">Standard eltolási és kivonási megközelítést használ a divízió megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="60974-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="60974-118">Az ellenőrzött verzió speciális, így a kivonás nem igényel további vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="60974-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>