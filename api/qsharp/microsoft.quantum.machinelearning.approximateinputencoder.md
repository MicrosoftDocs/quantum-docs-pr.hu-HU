---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856163"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="4a402-102">ApproximateInputEncoder függvény</span><span class="sxs-lookup"><span data-stu-id="4a402-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="4a402-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4a402-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4a402-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4a402-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4a402-105">Az egyes együtthatók és a tűréshatárok halmaza egy állapot-előkészítési műveletet ad vissza, amely az egyes együtthatókat a számítási állapot megfelelő amplitúdójának megfelelően, a megadott tűréshatárig állítja elő.</span><span class="sxs-lookup"><span data-stu-id="4a402-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="4a402-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4a402-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="4a402-107">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4a402-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4a402-108">A megadott együtthatók bemeneti állapotba való kódolásához használandó közelítési tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="4a402-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="4a402-109">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4a402-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4a402-110">A bemeneti állapotba kódolható együtthatók.</span><span class="sxs-lookup"><span data-stu-id="4a402-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="4a402-111">Kimenet: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="4a402-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="4a402-112">Állapot-előkészítési művelet, amely előkészíti az adott együtthatókat bemeneti állapotként egy adott regisztráción.</span><span class="sxs-lookup"><span data-stu-id="4a402-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>