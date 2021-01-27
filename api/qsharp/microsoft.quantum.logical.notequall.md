---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b19de2e4e8052c77118f341700357b212e20af53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849029"
---
# <a name="notequall-function"></a><span data-ttu-id="2db89-102">NotEqualL függvény</span><span class="sxs-lookup"><span data-stu-id="2db89-102">NotEqualL function</span></span>

<span data-ttu-id="2db89-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="2db89-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="2db89-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2db89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2db89-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="2db89-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="2db89-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2db89-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="2db89-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2db89-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2db89-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="2db89-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="2db89-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2db89-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="2db89-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="2db89-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2db89-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2db89-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2db89-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="2db89-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2db89-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2db89-113">Remarks</span></span>

<span data-ttu-id="2db89-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="2db89-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualL(a, b);
```