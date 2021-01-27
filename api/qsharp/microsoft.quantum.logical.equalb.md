---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817255"
---
# <a name="equalb-function"></a><span data-ttu-id="fa3ab-102">EqualB függvény</span><span class="sxs-lookup"><span data-stu-id="fa3ab-102">EqualB function</span></span>

<span data-ttu-id="fa3ab-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="fa3ab-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="fa3ab-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa3ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa3ab-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="fa3ab-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="fa3ab-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fa3ab-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="fa3ab-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa3ab-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa3ab-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="fa3ab-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="fa3ab-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa3ab-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa3ab-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="fa3ab-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fa3ab-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fa3ab-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fa3ab-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="fa3ab-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa3ab-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fa3ab-113">Remarks</span></span>

<span data-ttu-id="fa3ab-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="fa3ab-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```