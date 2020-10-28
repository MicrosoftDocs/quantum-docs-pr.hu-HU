---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709832"
---
# <a name="notequali-function"></a><span data-ttu-id="6e7b3-102">NotEqualI függvény</span><span class="sxs-lookup"><span data-stu-id="6e7b3-102">NotEqualI function</span></span>

<span data-ttu-id="6e7b3-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6e7b3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e7b3-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6e7b3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6e7b3-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6e7b3-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e7b3-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6e7b3-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e7b3-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="6e7b3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6e7b3-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6e7b3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6e7b3-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="6e7b3-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e7b3-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6e7b3-113">Remarks</span></span>

<span data-ttu-id="6e7b3-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="6e7b3-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```