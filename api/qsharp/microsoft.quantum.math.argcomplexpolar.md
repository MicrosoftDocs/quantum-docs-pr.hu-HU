---
uid: Microsoft.Quantum.Math.ArgComplexPolar
title: ArgComplexPolar függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ArgComplexPolar
qsharp.summary: Returns the phase of a complex number of type `ComplexPolar`.
ms.openlocfilehash: b4f2b9a192770f453302b469c80f03a9e57cf891
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723220"
---
# <a name="argcomplexpolar-function"></a><span data-ttu-id="93554-102">ArgComplexPolar függvény</span><span class="sxs-lookup"><span data-stu-id="93554-102">ArgComplexPolar function</span></span>

<span data-ttu-id="93554-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="93554-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="93554-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93554-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93554-105">Egy összetett számú típus fázisát adja vissza `ComplexPolar` .</span><span class="sxs-lookup"><span data-stu-id="93554-105">Returns the phase of a complex number of type `ComplexPolar`.</span></span>

```qsharp
function ArgComplexPolar (input : Microsoft.Quantum.Math.ComplexPolar) : Double
```


## <a name="input"></a><span data-ttu-id="93554-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="93554-106">Input</span></span>

### <a name="input--complexpolar"></a><span data-ttu-id="93554-107">bemenet: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="93554-107">input : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="93554-108">Komplex szám $c = r e ^ {i t} $.</span><span class="sxs-lookup"><span data-stu-id="93554-108">Complex number $c = r e^{i t}$.</span></span>



## <a name="output--double"></a><span data-ttu-id="93554-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="93554-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="93554-110">Fázis $ \text{Arg} [c] = t $.</span><span class="sxs-lookup"><span data-stu-id="93554-110">Phase $\text{Arg}[c] = t$.</span></span>