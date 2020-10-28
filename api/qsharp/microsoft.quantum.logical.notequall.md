---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f1d36c284293519e75e6c30ac64679c7bdf4609c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709805"
---
# <a name="notequall-function"></a><span data-ttu-id="4db9f-102">NotEqualL függvény</span><span class="sxs-lookup"><span data-stu-id="4db9f-102">NotEqualL function</span></span>

<span data-ttu-id="4db9f-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4db9f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4db9f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4db9f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4db9f-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="4db9f-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4db9f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4db9f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4db9f-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4db9f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4db9f-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="4db9f-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4db9f-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4db9f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4db9f-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="4db9f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4db9f-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4db9f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4db9f-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="4db9f-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4db9f-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4db9f-113">Remarks</span></span>

<span data-ttu-id="4db9f-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="4db9f-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualL(a, b);
```