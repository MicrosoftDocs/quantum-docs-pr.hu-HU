---
uid: Microsoft.Quantum.Logical.EqualL
title: Egyenrangú függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198112"
---
# <a name="equall-function"></a><span data-ttu-id="af162-102">Egyenrangú függvény</span><span class="sxs-lookup"><span data-stu-id="af162-102">EqualL function</span></span>

<span data-ttu-id="af162-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="af162-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="af162-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af162-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af162-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="af162-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="af162-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="af162-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="af162-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="af162-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="af162-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="af162-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="af162-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="af162-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="af162-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="af162-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="af162-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="af162-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="af162-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="af162-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="af162-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="af162-113">Remarks</span></span>

<span data-ttu-id="af162-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="af162-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```