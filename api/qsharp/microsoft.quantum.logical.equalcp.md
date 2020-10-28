---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: c8ee7e6a04cc2478f1c97fcc1d964a1574f7b1fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720760"
---
# <a name="equalcp-function"></a><span data-ttu-id="0c641-102">EqualCP függvény</span><span class="sxs-lookup"><span data-stu-id="0c641-102">EqualCP function</span></span>

<span data-ttu-id="0c641-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0c641-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0c641-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c641-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c641-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="0c641-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="0c641-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0c641-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="0c641-107">a: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="0c641-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="0c641-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="0c641-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="0c641-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="0c641-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="0c641-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="0c641-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0c641-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0c641-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0c641-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="0c641-112">`true` if and only if `a` is equal to `b`.</span></span>