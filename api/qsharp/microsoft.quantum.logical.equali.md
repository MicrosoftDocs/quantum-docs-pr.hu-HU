---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710056"
---
# <a name="equali-function"></a><span data-ttu-id="80f70-102">EqualI függvény</span><span class="sxs-lookup"><span data-stu-id="80f70-102">EqualI function</span></span>

<span data-ttu-id="80f70-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="80f70-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="80f70-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80f70-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80f70-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="80f70-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="80f70-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="80f70-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="80f70-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80f70-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80f70-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="80f70-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="80f70-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80f70-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80f70-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="80f70-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="80f70-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="80f70-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="80f70-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="80f70-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="80f70-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="80f70-113">Remarks</span></span>

<span data-ttu-id="80f70-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="80f70-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```