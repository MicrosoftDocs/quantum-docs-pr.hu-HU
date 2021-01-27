---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848218"
---
# <a name="squarednorm-function"></a><span data-ttu-id="12d20-102">SquaredNorm függvény</span><span class="sxs-lookup"><span data-stu-id="12d20-102">SquaredNorm function</span></span>

<span data-ttu-id="12d20-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="12d20-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="12d20-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="12d20-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="12d20-105">Egy vektor négyzetes 2 – normáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="12d20-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="12d20-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="12d20-106">Description</span></span>

<span data-ttu-id="12d20-107">Egy vektor négyzetes 2 – normáját adja vissza. Ez azt eredményezi, hogy a $ \vec{x} $ bemenet miatt a $ \ sum_i x_i ^ 2 $ értéket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="12d20-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="12d20-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="12d20-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="12d20-109">tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="12d20-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="12d20-110">Az a vektor, amelynek a négyzetes 2 normáját vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="12d20-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="12d20-111">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="12d20-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="12d20-112">A négyzetes 2 – norm `array` .</span><span class="sxs-lookup"><span data-stu-id="12d20-112">The squared 2-norm of `array`.</span></span>