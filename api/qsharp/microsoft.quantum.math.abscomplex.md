---
uid: Microsoft.Quantum.Math.AbsComplex
title: AbsComplex függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: AbsComplex
qsharp.summary: Returns the absolute value of a complex number of type `Complex`.
ms.openlocfilehash: 2bb4caa140bef36d893da834eac1c94b8dd8b0e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846068"
---
# <a name="abscomplex-function"></a><span data-ttu-id="23c05-102">AbsComplex függvény</span><span class="sxs-lookup"><span data-stu-id="23c05-102">AbsComplex function</span></span>

<span data-ttu-id="23c05-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="23c05-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="23c05-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23c05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23c05-105">Egy összetett számú típus abszolút értékét adja vissza `Complex` .</span><span class="sxs-lookup"><span data-stu-id="23c05-105">Returns the absolute value of a complex number of type `Complex`.</span></span>

```qsharp
function AbsComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="23c05-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="23c05-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="23c05-107">bemenet: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="23c05-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="23c05-108">Összetett szám $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="23c05-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="23c05-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="23c05-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="23c05-110">Abszolút érték $ | c | = \sqrt{x ^ 2 + y ^ 2} $.</span><span class="sxs-lookup"><span data-stu-id="23c05-110">Absolute value $|c| = \sqrt{x^2 + y^2}$.</span></span>