---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 5809b5463e6bf8ee73d095dfe4eafedfbb5e0702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852900"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="982e7-102">ArgComplexPolar függvény</span><span class="sxs-lookup"><span data-stu-id="982e7-102">ArgComplexPolar function</span></span>

<span data-ttu-id="982e7-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="982e7-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="982e7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="982e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="982e7-105">Egy összetett számú típus fázisát adja vissza `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="982e7-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="982e7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="982e7-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="982e7-107">bemenet: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="982e7-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="982e7-108">Komplex szám $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="982e7-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="982e7-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="982e7-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="982e7-110">Fázis $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="982e7-110">Phase $\text{Arg}[c] = t$.</span></span>