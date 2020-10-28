---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 8b0c34915ef392e8a84706f601da71f3848a3134
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720772"
---
# <a name="equalc-function"></a><span data-ttu-id="cd4bf-102">EqualC függvény</span><span class="sxs-lookup"><span data-stu-id="cd4bf-102">EqualC function</span></span>

<span data-ttu-id="cd4bf-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cd4bf-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cd4bf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd4bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd4bf-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="cd4bf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cd4bf-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="cd4bf-107">a: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="cd4bf-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="cd4bf-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="cd4bf-109">b: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="cd4bf-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="cd4bf-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="cd4bf-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cd4bf-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd4bf-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd4bf-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="cd4bf-112">`true` if and only if `a` is equal to `b`.</span></span>