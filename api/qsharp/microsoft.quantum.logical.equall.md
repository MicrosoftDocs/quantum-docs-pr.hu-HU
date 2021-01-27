---
uid: Microsoft.Quantum.Logical.EqualL
title: Egyenrangú függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815966"
---
# <a name="equall-function"></a><span data-ttu-id="e810e-102">Egyenrangú függvény</span><span class="sxs-lookup"><span data-stu-id="e810e-102">EqualL function</span></span>

<span data-ttu-id="e810e-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e810e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e810e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e810e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e810e-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="e810e-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e810e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e810e-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e810e-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e810e-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e810e-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="e810e-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e810e-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e810e-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e810e-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="e810e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e810e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e810e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e810e-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="e810e-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e810e-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e810e-113">Remarks</span></span>

<span data-ttu-id="e810e-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="e810e-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```