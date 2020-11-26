---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194729"
---
# <a name="pnorm-function"></a><span data-ttu-id="35a6a-102">PNorm függvény</span><span class="sxs-lookup"><span data-stu-id="35a6a-102">PNorm function</span></span>

<span data-ttu-id="35a6a-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="35a6a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="35a6a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35a6a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35a6a-105">Az `L(p)` s vektorának normáját adja vissza `Double` .</span><span class="sxs-lookup"><span data-stu-id="35a6a-105">Returns the `L(p)` norm of a vector of `Double`s.</span></span>

<span data-ttu-id="35a6a-106">Ez azt eredményezi, hogy egy tömb $x $ típusú `Double[]` , ez a következőt adja vissza: $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.</span><span class="sxs-lookup"><span data-stu-id="35a6a-106">That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.</span></span>

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a><span data-ttu-id="35a6a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="35a6a-107">Input</span></span>

### <a name="p--double"></a><span data-ttu-id="35a6a-108">p: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35a6a-108">p : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="35a6a-109">A kitevő $p $ a $p $-NORM.</span><span class="sxs-lookup"><span data-stu-id="35a6a-109">The exponent $p$ in the $p$-norm.</span></span>


### <a name="array--double"></a><span data-ttu-id="35a6a-110">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="35a6a-110">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>





## <a name="output--double"></a><span data-ttu-id="35a6a-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35a6a-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="35a6a-112">A $p $-norm $ \| x \| _p $.</span><span class="sxs-lookup"><span data-stu-id="35a6a-112">The $p$-norm $\|x\|_p$.</span></span>