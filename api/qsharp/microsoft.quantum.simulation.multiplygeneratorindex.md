---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: 9ee0568073b65b027cc98eb56934e9286b59c27f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724494"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="3f7cd-102">MultiplyGeneratorIndex függvény</span><span class="sxs-lookup"><span data-stu-id="3f7cd-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="3f7cd-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3f7cd-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3f7cd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f7cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f7cd-105">A együtthatót szorozza meg a-ben `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="3f7cd-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="3f7cd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3f7cd-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="3f7cd-107">szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f7cd-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f7cd-108">A szorzó a koefficiens alapján.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="3f7cd-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3f7cd-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3f7cd-110">A `GeneratorIndex` megszorozva.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="3f7cd-111">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3f7cd-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3f7cd-112">Egy olyan `GeneratorIndex` kifejezést jelöl, amelynek a faktora `multiplier` nagyobb.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f7cd-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3f7cd-113">See Also</span></span>

- [<span data-ttu-id="3f7cd-114">Microsoft. Quantum. szimulációs. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="3f7cd-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)