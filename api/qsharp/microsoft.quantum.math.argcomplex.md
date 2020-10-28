---
uid: Microsoft.Quantum.Math.ArgComplex
title: ArgComplex függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplex
qsharp.summary: Returns the phase of a complex number of type `Complex`.
ms.openlocfilehash: 629aa32ad80e5aa3d6f5ff75ac65df9b1a96fc15
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723263"
---
# <a name="argcomplex-function"></a><span data-ttu-id="2054f-102">ArgComplex függvény</span><span class="sxs-lookup"><span data-stu-id="2054f-102">ArgComplex function</span></span>

<span data-ttu-id="2054f-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2054f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2054f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2054f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2054f-105">Egy összetett számú típus fázisát adja vissza `Complex` .</span><span class="sxs-lookup"><span data-stu-id="2054f-105">Returns the phase of a complex number of type `Complex`.</span></span>

```qsharp
function ArgComplex (input : Microsoft.Quantum.Math.Complex) : Double
```


## <a name="input"></a><span data-ttu-id="2054f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2054f-106">Input</span></span>

### <a name="input--complex"></a><span data-ttu-id="2054f-107">bemenet: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="2054f-107">input : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="2054f-108">Összetett szám $c = x + i y $.</span><span class="sxs-lookup"><span data-stu-id="2054f-108">Complex number $c = x + i y$.</span></span>



## <a name="output--double"></a><span data-ttu-id="2054f-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2054f-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2054f-110">Fázis $ \text{Arg} [c] = \text{ArcTan} (y, x) \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="2054f-110">Phase $\text{Arg}[c] = \text{ArcTan}(y,x) \in (-\pi,\pi]$.</span></span>