---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: 7088397bd60e2779ef60afc1bb7108d937a62c97
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195766"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="dbc84-102">ArgComplexPolar függvény</span><span class="sxs-lookup"><span data-stu-id="dbc84-102">ArgComplexPolar function</span></span>

<span data-ttu-id="dbc84-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dbc84-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dbc84-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbc84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbc84-105">Egy összetett számú típus fázisát adja vissza `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="dbc84-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="dbc84-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dbc84-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="dbc84-107">bemenet: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="dbc84-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="dbc84-108">Komplex szám $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="dbc84-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="dbc84-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dbc84-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dbc84-110">Fázis $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="dbc84-110">Phase $\text{Arg}[c] = t$.</span></span>