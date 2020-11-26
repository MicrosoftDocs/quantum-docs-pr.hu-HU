---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliGenIdx
title: _ZTermToPauliGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: f4643ef03a0178f2c3ba1ea68f36f2f3fcd7b9ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215027"
---
# <a name="_ztermtopauligenidx-function"></a><span data-ttu-id="557d2-102">_ZTermToPauliGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="557d2-102">_ZTermToPauliGenIdx function</span></span>

<span data-ttu-id="557d2-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="557d2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="557d2-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="557d2-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="557d2-105">Egy "Z" kifejezésre mutató GeneratorIndex alakít át egy "GeneratorIndex []" kifejezésre.</span><span class="sxs-lookup"><span data-stu-id="557d2-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="557d2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="557d2-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="557d2-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="557d2-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="557d2-108">`GeneratorIndex` egy Z kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="557d2-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="557d2-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="557d2-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="557d2-110">"GeneratorIndex []" kifejezés, amely a Z "Pauli" kifejezéssel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="557d2-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>