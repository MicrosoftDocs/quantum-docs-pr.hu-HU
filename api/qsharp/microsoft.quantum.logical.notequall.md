---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: e138a8def30bc77499662ffa6bc214d0c6a38893
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197228"
---
# <a name="notequall-function"></a><span data-ttu-id="1951e-102">NotEqualL függvény</span><span class="sxs-lookup"><span data-stu-id="1951e-102">NotEqualL function</span></span>

<span data-ttu-id="1951e-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1951e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1951e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1951e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1951e-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="1951e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="1951e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1951e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1951e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1951e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1951e-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="1951e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="1951e-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1951e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1951e-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="1951e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1951e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1951e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1951e-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="1951e-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1951e-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1951e-113">Remarks</span></span>

<span data-ttu-id="1951e-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="1951e-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```