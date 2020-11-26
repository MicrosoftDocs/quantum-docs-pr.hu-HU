---
uid: Microsoft.Quantum.Math.AbsSquaredComplex
title: AbsSquaredComplex függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsSquaredComplex
qsharp.summary: Returns the squared absolute value of a complex number of type `Complex`.
ms.openlocfilehash: d48212d7f861b3ff9e37d078742f53f0cd8c71ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195902"
---
# <a name="abssquaredcomplex-function"></a><span data-ttu-id="b1190-102">AbsSquaredComplex függvény</span><span class="sxs-lookup"><span data-stu-id="b1190-102">AbsSquaredComplex function</span></span>

<span data-ttu-id="b1190-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b1190-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b1190-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1190-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1190-105">Egy komplex számú típus négyzetes abszolút értékét adja vissza `Complex` .</span><span class="sxs-lookup"><span data-stu-id="b1190-105">Returns the squared absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsSquaredComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="b1190-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b1190-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="b1190-107">bemenet: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b1190-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b1190-108">Összetett szám $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="b1190-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="b1190-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b1190-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b1190-110">Négyzetes abszolút érték: $ | c | ^ 2 = x ^ 2 + y ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="b1190-110">Squared absolute value $|c|^2 = x^2 + y^2$.</span></span>