---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _PQTermToPauliGenIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 7f1794f9e46323ccf722407fb7ae82f73ed76e40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215435"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="0f557-102">_PQTermToPauliGenIdx_ függvény</span><span class="sxs-lookup"><span data-stu-id="0f557-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="0f557-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0f557-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0f557-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0f557-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0f557-105">A "GeneratorIndex []" kifejezésre a "GeneratorIndex" kifejezést leíró kifejezést alakít át Pál</span><span class="sxs-lookup"><span data-stu-id="0f557-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="0f557-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0f557-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="0f557-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0f557-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0f557-108">`GeneratorIndex` egy PQ kifejezést jelölő kifejezés.</span><span class="sxs-lookup"><span data-stu-id="0f557-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="0f557-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="0f557-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="0f557-110">A "GeneratorIndex []" kifejezésben a PQ kifejezést Pauli-kifejezésként fejezi ki.</span><span class="sxs-lookup"><span data-stu-id="0f557-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>