---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720233"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="80b02-102">MultiplyGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="80b02-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="80b02-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="80b02-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="80b02-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80b02-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80b02-105">Az a összes kifejezés együtthatójának szorzata `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="80b02-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="80b02-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="80b02-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="80b02-107">szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="80b02-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="80b02-108">A szorzó a koefficiens alapján.</span><span class="sxs-lookup"><span data-stu-id="80b02-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="80b02-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="80b02-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="80b02-110">A `GeneratorSystem` megszorozva.</span><span class="sxs-lookup"><span data-stu-id="80b02-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="80b02-111">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="80b02-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="80b02-112">Egy olyan `GeneratorSystem` rendszer, amely együtthatókkal nagyobb tényezőt jelent `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="80b02-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="80b02-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="80b02-113">See Also</span></span>

- [<span data-ttu-id="80b02-114">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="80b02-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)