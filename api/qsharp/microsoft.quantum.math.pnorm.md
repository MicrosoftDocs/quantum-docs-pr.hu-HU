---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722297"
---
# <a name="pnorm-function"></a><span data-ttu-id="5c5ba-102">PNorm függvény</span><span class="sxs-lookup"><span data-stu-id="5c5ba-102">PNorm function</span></span>

<span data-ttu-id="5c5ba-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5c5ba-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5c5ba-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c5ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c5ba-105">Az `L(p)` s vektorának normáját adja vissza `Double` .</span><span class="sxs-lookup"><span data-stu-id="5c5ba-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="5c5ba-106">Ez azt eredményezi, hogy egy tömb $x $ típusú `Double[]` , ez a következőt adja vissza: $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="5c5ba-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="5c5ba-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5c5ba-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="5c5ba-108">p: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5c5ba-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5c5ba-109">A kitevő $p $ a $p $-NORM.</span><span class="sxs-lookup"><span data-stu-id="5c5ba-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="5c5ba-110">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5c5ba-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="5c5ba-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5c5ba-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5c5ba-112">A $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="5c5ba-112">The $p$-norm $\|x\|_p$.</span></span>