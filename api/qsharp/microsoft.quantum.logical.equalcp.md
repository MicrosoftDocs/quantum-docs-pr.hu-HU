---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: e3175b9b6fd2890963de0452102e2f0de1026b91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198231"
---
# <a name="equalcp-function"></a><span data-ttu-id="7d8b2-102">EqualCP függvény</span><span class="sxs-lookup"><span data-stu-id="7d8b2-102">EqualCP function</span></span>

<span data-ttu-id="7d8b2-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7d8b2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7d8b2-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d8b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d8b2-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="7d8b2-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="7d8b2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7d8b2-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="7d8b2-107">a: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7d8b2-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7d8b2-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="7d8b2-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="7d8b2-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7d8b2-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7d8b2-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="7d8b2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7d8b2-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d8b2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d8b2-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="7d8b2-112">`true` if and only if `a` is equal to `b`.</span></span>