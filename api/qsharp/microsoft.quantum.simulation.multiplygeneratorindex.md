---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorIndex
title: MultiplyGeneratorIndex függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorIndex
qsharp.summary: Multiplies the coefficient in a `GeneratorIndex`.
ms.openlocfilehash: dc2bd02c40b53eca726f70578e3c5918add8f1bb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230446"
---
# <a name="multiplygeneratorindex-function"></a><span data-ttu-id="7da8e-102">MultiplyGeneratorIndex függvény</span><span class="sxs-lookup"><span data-stu-id="7da8e-102">MultiplyGeneratorIndex function</span></span>

<span data-ttu-id="7da8e-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7da8e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7da8e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7da8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7da8e-105">A együtthatót szorozza meg a-ben `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="7da8e-105">Multiplies the coefficient in a `GeneratorIndex`.</span></span>

```qsharp
function MultiplyGeneratorIndex (multiplier : Double, generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="7da8e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7da8e-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="7da8e-107">szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7da8e-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7da8e-108">A szorzó a koefficiens alapján.</span><span class="sxs-lookup"><span data-stu-id="7da8e-108">The multiplier on the coefficient.</span></span>


### <a name="generatorindex--generatorindex"></a><span data-ttu-id="7da8e-109">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7da8e-109">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7da8e-110">A `GeneratorIndex` megszorozva.</span><span class="sxs-lookup"><span data-stu-id="7da8e-110">The `GeneratorIndex` to be multiplied.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="7da8e-111">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="7da8e-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="7da8e-112">Egy olyan `GeneratorIndex` kifejezést jelöl, amelynek a faktora `multiplier` nagyobb.</span><span class="sxs-lookup"><span data-stu-id="7da8e-112">A `GeneratorIndex` representing a term with coefficient a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="7da8e-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7da8e-113">See Also</span></span>

- [<span data-ttu-id="7da8e-114">Microsoft. Quantum. szimulációs. GeneratorIndex</span><span class="sxs-lookup"><span data-stu-id="7da8e-114">Microsoft.Quantum.Simulation.GeneratorIndex</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorIndex)