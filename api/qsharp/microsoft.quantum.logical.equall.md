---
uid: Microsoft.Quantum.Logical.EqualL
title: Egyenrangú függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f0a2bfa866068746e9c6e249573eb61c0d08c0f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710042"
---
# <a name="equall-function"></a><span data-ttu-id="bc6a0-102">Egyenrangú függvény</span><span class="sxs-lookup"><span data-stu-id="bc6a0-102">EqualL function</span></span>

<span data-ttu-id="bc6a0-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="bc6a0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="bc6a0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc6a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc6a0-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="bc6a0-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="bc6a0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc6a0-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="bc6a0-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bc6a0-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bc6a0-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="bc6a0-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="bc6a0-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bc6a0-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bc6a0-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="bc6a0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bc6a0-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bc6a0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bc6a0-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="bc6a0-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc6a0-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bc6a0-113">Remarks</span></span>

<span data-ttu-id="bc6a0-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="bc6a0-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```