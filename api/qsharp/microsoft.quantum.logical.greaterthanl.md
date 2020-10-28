---
uid: Microsoft.Quantum.Logical.GreaterThanL
title: GreaterThanL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanL
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 676defa7824e53578504c559c6d8f24b2ffc1a88
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711386"
---
# <a name="greaterthanl-function"></a><span data-ttu-id="0af38-102">GreaterThanL függvény</span><span class="sxs-lookup"><span data-stu-id="0af38-102">GreaterThanL function</span></span>

<span data-ttu-id="0af38-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0af38-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0af38-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0af38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0af38-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="0af38-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="0af38-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0af38-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0af38-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0af38-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0af38-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="0af38-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="0af38-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0af38-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0af38-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="0af38-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0af38-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0af38-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0af38-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="0af38-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0af38-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0af38-113">Remarks</span></span>

<span data-ttu-id="0af38-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="0af38-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanL(a, b);
```