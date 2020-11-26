---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 196bdab67528aa8672a010ac3830459e27276ce9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227522"
---
# <a name="pnormalized-function"></a><span data-ttu-id="76d66-102">PNormalized függvény</span><span class="sxs-lookup"><span data-stu-id="76d66-102">PNormalized function</span></span>

<span data-ttu-id="76d66-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="76d66-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="76d66-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="76d66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="76d66-105">Normalizálja `Double` az s-vektort a `L(p)` normában.</span><span class="sxs-lookup"><span data-stu-id="76d66-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="76d66-106">Ez azt eredményezi, hogy egy Array $x $ típusú tömbben `Double[]` olyan tömböt ad vissza, amelyben az összes elem a $p $-norm $ \| x _p $ értékkel van elosztva \| .</span><span class="sxs-lookup"><span data-stu-id="76d66-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="76d66-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="76d66-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="76d66-108">p: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="76d66-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="76d66-109">A kitevő $p $ a $p $-NORM.</span><span class="sxs-lookup"><span data-stu-id="76d66-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="76d66-110">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="76d66-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="76d66-111">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="76d66-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="76d66-112">A $p $-norm $ \| x _p $ $x által normalizált tömb \| .</span><span class="sxs-lookup"><span data-stu-id="76d66-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="76d66-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="76d66-113">See Also</span></span>

- [<span data-ttu-id="76d66-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="76d66-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)