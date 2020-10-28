---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 212ed4c473fab3572f73ea250061057ad13e393f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709440"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="4167c-102">InterpolateGeneratorSystemsImpl függvény</span><span class="sxs-lookup"><span data-stu-id="4167c-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="4167c-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4167c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4167c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4167c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4167c-105">A lineárisan interpolált két `GeneratorSystems` érték között egy `s` 0 és 1 közötti Schedule paraméter (beleértve a (z) függvényt).</span><span class="sxs-lookup"><span data-stu-id="4167c-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="4167c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4167c-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="4167c-107">ütemterv: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4167c-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4167c-108">Egy Schedule paraméter $s \in [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="4167c-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="4167c-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4167c-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="4167c-110">Az indítás `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="4167c-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="4167c-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4167c-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="4167c-112">A vége `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="4167c-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="4167c-113">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4167c-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="4167c-114">A egy olyan `GeneratorSystem` rendszert képvisel, amely a bemeneti létrehozó rendszerek összege, amelynek súlya $ (1-s) $, `generatorSystemStart` és súlyozás $s $ `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="4167c-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4167c-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4167c-115">See Also</span></span>

- [<span data-ttu-id="4167c-116">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="4167c-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)