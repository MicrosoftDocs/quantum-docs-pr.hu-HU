---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: effb9e3ca754f77bbe1ea0fb6ca30ae49e92d531
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229154"
---
# <a name="multiplygeneratorsystem-function"></a><span data-ttu-id="535c4-102">MultiplyGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="535c4-102">MultiplyGeneratorSystem function</span></span>

<span data-ttu-id="535c4-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="535c4-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="535c4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="535c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="535c4-105">Az a összes kifejezés együtthatójának szorzata `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="535c4-105">Multiplies the coefficient of all terms in a `GeneratorSystem`.</span></span>

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="535c4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="535c4-106">Input</span></span>

### <a name="multiplier--double"></a><span data-ttu-id="535c4-107">szorzó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="535c4-107">multiplier : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="535c4-108">A szorzó a koefficiens alapján.</span><span class="sxs-lookup"><span data-stu-id="535c4-108">The multiplier on the coefficient.</span></span>


### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="535c4-109">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="535c4-109">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="535c4-110">A `GeneratorSystem` megszorozva.</span><span class="sxs-lookup"><span data-stu-id="535c4-110">The `GeneratorSystem` to be multiplied.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="535c4-111">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="535c4-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="535c4-112">Egy olyan `GeneratorSystem` rendszer, amely együtthatókkal nagyobb tényezőt jelent `multiplier` .</span><span class="sxs-lookup"><span data-stu-id="535c4-112">A `GeneratorSystem` representing a system with coefficients a factor `multiplier` larger.</span></span>

## <a name="see-also"></a><span data-ttu-id="535c4-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="535c4-113">See Also</span></span>

- [<span data-ttu-id="535c4-114">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="535c4-114">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)