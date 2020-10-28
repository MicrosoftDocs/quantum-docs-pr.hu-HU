---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 20414e80e08993a18331a8f0b385a1e4cc1255b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710001"
---
# <a name="greaterthand-function"></a><span data-ttu-id="080a1-102">GreaterThanD függvény</span><span class="sxs-lookup"><span data-stu-id="080a1-102">GreaterThanD function</span></span>

<span data-ttu-id="080a1-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="080a1-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="080a1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="080a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="080a1-105">Igaz értéket ad vissza, és csak akkor, ha egy szám nagyobb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="080a1-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="080a1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="080a1-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="080a1-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="080a1-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="080a1-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="080a1-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="080a1-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="080a1-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="080a1-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="080a1-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="080a1-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="080a1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="080a1-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan nagyobb, mint `b` .</span><span class="sxs-lookup"><span data-stu-id="080a1-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="080a1-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="080a1-113">Remarks</span></span>

<span data-ttu-id="080a1-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="080a1-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```