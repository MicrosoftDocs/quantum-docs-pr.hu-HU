---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 0be2c97ec7b0350fc20eace76746f3ffff65fd52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197364"
---
# <a name="notequalc-function"></a><span data-ttu-id="66c1f-102">NotEqualC függvény</span><span class="sxs-lookup"><span data-stu-id="66c1f-102">NotEqualC function</span></span>

<span data-ttu-id="66c1f-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="66c1f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="66c1f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66c1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66c1f-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="66c1f-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="66c1f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="66c1f-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="66c1f-107">a: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="66c1f-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="66c1f-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="66c1f-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="66c1f-109">b: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="66c1f-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="66c1f-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="66c1f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="66c1f-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="66c1f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="66c1f-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="66c1f-112">`true` if and only if `a` is not equal to `b`.</span></span>