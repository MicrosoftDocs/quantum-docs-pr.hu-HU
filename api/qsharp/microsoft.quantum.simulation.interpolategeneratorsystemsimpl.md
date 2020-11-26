---
uid: Microsoft.Quantum.Simulation.InterpolateGeneratorSystemsImpl
title: InterpolateGeneratorSystemsImpl függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolateGeneratorSystemsImpl
qsharp.summary: Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).
ms.openlocfilehash: 1ca9580ba603db8fee40e008a7ea51cb7a04d7d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229222"
---
# <a name="interpolategeneratorsystemsimpl-function"></a><span data-ttu-id="a4839-102">InterpolateGeneratorSystemsImpl függvény</span><span class="sxs-lookup"><span data-stu-id="a4839-102">InterpolateGeneratorSystemsImpl function</span></span>

<span data-ttu-id="a4839-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a4839-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a4839-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4839-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4839-105">A lineárisan interpolált két `GeneratorSystems` érték között egy `s` 0 és 1 közötti Schedule paraméter (beleértve a (z) függvényt).</span><span class="sxs-lookup"><span data-stu-id="a4839-105">Linearly interpolates between two `GeneratorSystems` according to a schedule parameter `s` between 0 and 1 (inclusive).</span></span>

```qsharp
function InterpolateGeneratorSystemsImpl (schedule : Double, generatorSystemStart : Microsoft.Quantum.Simulation.GeneratorSystem, generatorSystemEnd : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a4839-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a4839-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="a4839-107">ütemterv: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a4839-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a4839-108">Egy Schedule paraméter $s \in [0, 1] $.</span><span class="sxs-lookup"><span data-stu-id="a4839-108">A schedule parameter $s\in[0,1]$.</span></span>


### <a name="generatorsystemstart--generatorsystem"></a><span data-ttu-id="a4839-109">generatorSystemStart: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a4839-109">generatorSystemStart : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a4839-110">Az indítás `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="a4839-110">The start `GeneratorSystem`.</span></span>


### <a name="generatorsystemend--generatorsystem"></a><span data-ttu-id="a4839-111">generatorSystemEnd: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a4839-111">generatorSystemEnd : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a4839-112">A vége `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="a4839-112">The end `GeneratorSystem`.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a4839-113">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a4839-113">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a4839-114">A egy olyan `GeneratorSystem` rendszert képvisel, amely a bemeneti létrehozó rendszerek összege, amelynek súlya $ (1-s) $, `generatorSystemStart` és súlyozás $s $ `generatorSystemEnd` .</span><span class="sxs-lookup"><span data-stu-id="a4839-114">A `GeneratorSystem` representing a system that is the sum of the input generator systems, with weight $(1-s)$ on `generatorSystemStart` and weight $s$ on `generatorSystemEnd`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4839-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a4839-115">See Also</span></span>

- [<span data-ttu-id="a4839-116">Microsoft. Quantum. szimulációs. GeneratorSystem</span><span class="sxs-lookup"><span data-stu-id="a4839-116">Microsoft.Quantum.Simulation.GeneratorSystem</span></span>](xref:Microsoft.Quantum.Simulation.GeneratorSystem)