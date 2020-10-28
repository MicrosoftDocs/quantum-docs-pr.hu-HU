---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: d5a9819bf3baa7c914487277fef308abbc8d25bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709833"
---
# <a name="notequalb-function"></a><span data-ttu-id="6e478-102">NotEqualB függvény</span><span class="sxs-lookup"><span data-stu-id="6e478-102">NotEqualB function</span></span>

<span data-ttu-id="6e478-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6e478-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6e478-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e478-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e478-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="6e478-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="6e478-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6e478-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="6e478-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6e478-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6e478-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="6e478-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="6e478-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6e478-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6e478-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="6e478-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6e478-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6e478-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6e478-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="6e478-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e478-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6e478-113">Remarks</span></span>

<span data-ttu-id="6e478-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="6e478-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualB(a, b);
```