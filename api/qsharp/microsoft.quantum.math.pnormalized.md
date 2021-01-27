---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854847"
---
# <a name="pnormalized-function"></a><span data-ttu-id="51c51-102">PNormalized függvény</span><span class="sxs-lookup"><span data-stu-id="51c51-102">PNormalized function</span></span>

<span data-ttu-id="51c51-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="51c51-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="51c51-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51c51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51c51-105">Normalizálja `Double` az s-vektort a `L(p)` normában.</span><span class="sxs-lookup"><span data-stu-id="51c51-105">Normalizes a vector of `Double`s in the `L(p)` norm.</span></span>

<span data-ttu-id="51c51-106">Ez azt eredményezi, hogy egy Array $x $ típusú tömbben `Double[]` olyan tömböt ad vissza, amelyben az összes elem a $p $-norm $ \| x _p $ értékkel van elosztva \| .</span><span class="sxs-lookup"><span data-stu-id="51c51-106">That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.</span></span>

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a><span data-ttu-id="51c51-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="51c51-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="51c51-108">p: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="51c51-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="51c51-109">A kitevő $p $ a $p $-NORM.</span><span class="sxs-lookup"><span data-stu-id="51c51-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="51c51-110">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="51c51-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="51c51-111">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="51c51-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="51c51-112">A $p $-norm $ \| x _p $ $x által normalizált tömb \| .</span><span class="sxs-lookup"><span data-stu-id="51c51-112">The array $x$ normalized by the $p$-norm $\|x\|_p$.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c51-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="51c51-113">See Also</span></span>

- [<span data-ttu-id="51c51-114">Microsoft. Quantum. Math. PNorm</span><span class="sxs-lookup"><span data-stu-id="51c51-114">Microsoft.Quantum.Math.PNorm</span></span>](xref:Microsoft.Quantum.Math.PNorm)