---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _ZTermToPauliMajIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 13897d831bc3382dbb23b653c5905978330eb622
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214993"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="f2943-102">_ZTermToPauliMajIdx_ függvény</span><span class="sxs-lookup"><span data-stu-id="f2943-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="f2943-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f2943-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f2943-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f2943-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f2943-105">Egy "Z" kifejezésre mutató GeneratorIndex alakít át egy "GeneratorIndex []" kifejezésre.</span><span class="sxs-lookup"><span data-stu-id="f2943-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="f2943-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f2943-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f2943-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f2943-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f2943-108">`GeneratorIndex` egy Z kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="f2943-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="f2943-109">Kimenet: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="f2943-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="f2943-110">"GeneratorIndex []" kifejezés, amely a Z "Pauli" kifejezéssel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="f2943-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>