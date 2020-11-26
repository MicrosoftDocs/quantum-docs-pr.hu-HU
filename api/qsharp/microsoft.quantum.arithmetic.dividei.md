---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223306"
---
# <a name="dividei-operation"></a><span data-ttu-id="b0e68-102">DivideI művelet</span><span class="sxs-lookup"><span data-stu-id="b0e68-102">DivideI operation</span></span>

<span data-ttu-id="b0e68-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b0e68-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b0e68-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="b0e68-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="b0e68-105">Két kvantum egész számot oszt ki.</span><span class="sxs-lookup"><span data-stu-id="b0e68-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b0e68-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b0e68-106">Description</span></span>

<span data-ttu-id="b0e68-107">`xs` a maradékot fogja tárolni `xs - floor(xs/ys) * ys` , és `result` megtartja `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="b0e68-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="b0e68-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b0e68-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b0e68-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0e68-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0e68-110">$n $-bit osztalékot, a fennmaradó összeg helyébe lép.</span><span class="sxs-lookup"><span data-stu-id="b0e68-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b0e68-111">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="b0e68-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0e68-112">$n $ bites osztó</span><span class="sxs-lookup"><span data-stu-id="b0e68-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="b0e68-113">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0e68-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b0e68-114">$n $-bit eredménynek kezdetben a $ \ket $ állapotban kell lennie, {0} és a rendszer az egész szám felosztásával váltja fel.</span><span class="sxs-lookup"><span data-stu-id="b0e68-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0e68-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0e68-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0e68-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b0e68-116">Remarks</span></span>

<span data-ttu-id="b0e68-117">Standard eltolási és kivonási megközelítést használ a divízió megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="b0e68-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="b0e68-118">Az ellenőrzött verzió speciális, így a kivonás nem igényel további vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="b0e68-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>