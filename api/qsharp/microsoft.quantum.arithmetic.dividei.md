---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846684"
---
# <a name="dividei-operation"></a><span data-ttu-id="82c30-102">DivideI művelet</span><span class="sxs-lookup"><span data-stu-id="82c30-102">DivideI operation</span></span>

<span data-ttu-id="82c30-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="82c30-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="82c30-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="82c30-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="82c30-105">Két kvantum egész számot oszt ki.</span><span class="sxs-lookup"><span data-stu-id="82c30-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="82c30-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="82c30-106">Description</span></span>

<span data-ttu-id="82c30-107">`xs` a maradékot fogja tárolni `xs - floor(xs/ys) * ys` , és `result` megtartja `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="82c30-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="82c30-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="82c30-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="82c30-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="82c30-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="82c30-110">$n $-bit osztalékot, a fennmaradó összeg helyébe lép.</span><span class="sxs-lookup"><span data-stu-id="82c30-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="82c30-111">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="82c30-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="82c30-112">$n $ bites osztó</span><span class="sxs-lookup"><span data-stu-id="82c30-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="82c30-113">eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="82c30-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="82c30-114">$n $-bit eredménynek kezdetben a $ \ket $ állapotban kell lennie, {0} és a rendszer az egész szám felosztásával váltja fel.</span><span class="sxs-lookup"><span data-stu-id="82c30-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82c30-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82c30-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="82c30-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="82c30-116">Remarks</span></span>

<span data-ttu-id="82c30-117">Standard eltolási és kivonási megközelítést használ a divízió megvalósításához.</span><span class="sxs-lookup"><span data-stu-id="82c30-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="82c30-118">Az ellenőrzött verzió speciális, így a kivonás nem igényel további vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="82c30-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>