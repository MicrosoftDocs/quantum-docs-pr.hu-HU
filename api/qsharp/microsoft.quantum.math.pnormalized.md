---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722283"
---
# <a name="pnormalized-function"></a><span data-ttu-id="ba40d-102">PNormalized függvény</span><span class="sxs-lookup"><span data-stu-id="ba40d-102">PNormalized function</span></span>

<span data-ttu-id="ba40d-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ba40d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ba40d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ba40d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ba40d-105">Normalizálja `Double` az s-vektort a `L(p)` normában.</span><span class="sxs-lookup"><span data-stu-id="ba40d-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="ba40d-106">Ez azt eredményezi, hogy egy Array $x $ típusú tömbben `Double[]` olyan tömböt ad vissza, amelyben az összes elem a $p $-norm $ \| x _p $ értékkel van elosztva \| .</span><span class="sxs-lookup"><span data-stu-id="ba40d-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="ba40d-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ba40d-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="ba40d-108">p: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ba40d-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ba40d-109">A kitevő $p $ a $p $-NORM.</span><span class="sxs-lookup"><span data-stu-id="ba40d-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="ba40d-110">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ba40d-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="ba40d-111">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ba40d-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ba40d-112">A $p $-norm $ \| x _p $ $x által normalizált tömb \| .</span><span class="sxs-lookup"><span data-stu-id="ba40d-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba40d-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ba40d-113">See Also</span></span>

- [<span data-ttu-id="ba40d-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="ba40d-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)