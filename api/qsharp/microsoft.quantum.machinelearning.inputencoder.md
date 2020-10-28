---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709749"
---
# <a name="inputencoder-function"></a><span data-ttu-id="f92a0-102">InputEncoder függvény</span><span class="sxs-lookup"><span data-stu-id="f92a0-102">InputEncoder function</span></span>

<span data-ttu-id="f92a0-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f92a0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f92a0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f92a0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f92a0-105">Az együtthatók és a tűréshatárok halmaza egy állapot-előkészítési műveletet ad vissza, amely az egyes együtthatókat a számítási állapot megfelelő amplitúdójának megfelelően készíti elő.</span><span class="sxs-lookup"><span data-stu-id="f92a0-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="f92a0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f92a0-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="f92a0-107">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f92a0-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f92a0-108">A bemeneti állapotba kódolható együtthatók.</span><span class="sxs-lookup"><span data-stu-id="f92a0-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="f92a0-109">Kimenet: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="f92a0-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="f92a0-110">Állapot-előkészítési művelet, amely előkészíti az adott együtthatókat bemeneti állapotként egy adott regisztráción.</span><span class="sxs-lookup"><span data-stu-id="f92a0-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>