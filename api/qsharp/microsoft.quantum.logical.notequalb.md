---
uid: Microsoft.Quantum.Logical.NotEqualB
title: NotEqualB függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualB
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 9f362b9e08f8a798bf7f7d9c323fee6576dccd9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814426"
---
# <a name="notequalb-function"></a><span data-ttu-id="63525-102">NotEqualB függvény</span><span class="sxs-lookup"><span data-stu-id="63525-102">NotEqualB function</span></span>

<span data-ttu-id="63525-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="63525-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="63525-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63525-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63525-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="63525-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="63525-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="63525-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="63525-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63525-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63525-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="63525-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="63525-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63525-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63525-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="63525-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="63525-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63525-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63525-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="63525-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="63525-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="63525-113">Remarks</span></span>

<span data-ttu-id="63525-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="63525-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualB(a, b);
```