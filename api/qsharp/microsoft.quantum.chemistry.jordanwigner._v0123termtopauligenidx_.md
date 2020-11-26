---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: fc5ad0e97374c52a90012b0ce633af8488f3ad88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215095"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="f3d6c-102">_V0123TermToPauliGenIdx_ függvény</span><span class="sxs-lookup"><span data-stu-id="f3d6c-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="f3d6c-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f3d6c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f3d6c-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f3d6c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f3d6c-105">A PQRS kifejezést leíró GeneratorIndex alakítja át a (z) "GeneratorIndex []" kifejezésre a Paulis alapján</span><span class="sxs-lookup"><span data-stu-id="f3d6c-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="f3d6c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f3d6c-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f3d6c-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f3d6c-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f3d6c-108">`GeneratorIndex` PQRS kifejezés.</span><span class="sxs-lookup"><span data-stu-id="f3d6c-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f3d6c-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="f3d6c-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="f3d6c-110">A "GeneratorIndex []" kifejezés a PQRS kifejezést a Pauli kifejezésként fejezi ki.</span><span class="sxs-lookup"><span data-stu-id="f3d6c-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>