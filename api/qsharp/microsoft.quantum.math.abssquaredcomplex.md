---
uid: Microsoft.Quantum.Math.AbsSquaredComplex
title: AbsSquaredComplex függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsSquaredComplex
qsharp.summary: Returns the squared absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 5e08f76a175abdcd96b493a5708b3e5fc18eda61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857579"
---
# <a name="abssquaredcomplex-function"></a><span data-ttu-id="b0134-102">AbsSquaredComplex függvény</span><span class="sxs-lookup"><span data-stu-id="b0134-102">AbsSquaredComplex function</span></span>

<span data-ttu-id="b0134-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b0134-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b0134-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0134-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0134-105">Egy komplex számú típus négyzetes abszolút értékét adja vissza `Complex` .</span><span class="sxs-lookup"><span data-stu-id="b0134-105">Returns the squared absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsSquaredComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="b0134-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b0134-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="b0134-107">bemenet: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b0134-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b0134-108">Összetett szám $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="b0134-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="b0134-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0134-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0134-110">Négyzetes abszolút érték: $ | c | ^ 2 = x ^ 2 + y ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="b0134-110">Squared absolute value $|c|^2 = x^2 + y^2$.</span></span>