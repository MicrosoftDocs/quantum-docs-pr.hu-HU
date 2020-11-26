---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d9afb4b9b37b6cdd83bfd3829d3174d769c5f41b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211389"
---
# <a name="abscomplex-function"></a><span data-ttu-id="8f3c3-102">AbsComplex függvény</span><span class="sxs-lookup"><span data-stu-id="8f3c3-102">AbsComplex function</span></span>

<span data-ttu-id="8f3c3-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8f3c3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8f3c3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f3c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f3c3-105">Egy összetett számú típus abszolút értékét adja vissza `Complex` .</span><span class="sxs-lookup"><span data-stu-id="8f3c3-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="8f3c3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8f3c3-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="8f3c3-107">bemenet: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="8f3c3-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="8f3c3-108">Összetett szám $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="8f3c3-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="8f3c3-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f3c3-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f3c3-110">Abszolút érték $ | c | = \sqrt{x ^ 2 + y ^ 2} $.</span><span class="sxs-lookup"><span data-stu-id="8f3c3-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>