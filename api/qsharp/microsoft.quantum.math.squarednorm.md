---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725026"
---
# <a name="squarednorm-function"></a><span data-ttu-id="82171-102">SquaredNorm függvény</span><span class="sxs-lookup"><span data-stu-id="82171-102">SquaredNorm function</span></span>

<span data-ttu-id="82171-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="82171-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="82171-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82171-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82171-105">Egy vektor négyzetes 2 – normáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="82171-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="82171-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="82171-106">Description</span></span>

<span data-ttu-id="82171-107">Egy vektor négyzetes 2 – normáját adja vissza. Ez azt eredményezi, hogy a $ \vec{x} $ bemenet miatt a $ \ sum_i x_i ^ 2 $ értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="82171-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="82171-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="82171-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="82171-109">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="82171-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="82171-110">Az a vektor, amelynek a négyzetes 2 normáját vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="82171-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="82171-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="82171-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="82171-112">A négyzetes 2 – norm `array` .</span><span class="sxs-lookup"><span data-stu-id="82171-112">The squared 2-norm of `array`.</span></span>