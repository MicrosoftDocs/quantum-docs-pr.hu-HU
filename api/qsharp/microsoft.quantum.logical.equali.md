---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 87cf00ea8bb738cda30092b3d80940291beb1fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816749"
---
# <a name="equali-function"></a><span data-ttu-id="deb66-102">EqualI függvény</span><span class="sxs-lookup"><span data-stu-id="deb66-102">EqualI function</span></span>

<span data-ttu-id="deb66-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="deb66-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="deb66-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="deb66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="deb66-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="deb66-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="deb66-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="deb66-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="deb66-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="deb66-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="deb66-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="deb66-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="deb66-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="deb66-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="deb66-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="deb66-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="deb66-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="deb66-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="deb66-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="deb66-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="deb66-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="deb66-113">Remarks</span></span>

<span data-ttu-id="deb66-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="deb66-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualI(a, b);
```