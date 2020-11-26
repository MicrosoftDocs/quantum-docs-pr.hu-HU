---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _PQTermToPauliMajIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: bb9fad038c30b3362ffbecf546bcf85cb7dd13df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215401"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="fc6fb-102">_PQTermToPauliMajIdx_ függvény</span><span class="sxs-lookup"><span data-stu-id="fc6fb-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="fc6fb-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="fc6fb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="fc6fb-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="fc6fb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="fc6fb-105">A "GeneratorIndex []" kifejezésre a "GeneratorIndex" kifejezést leíró kifejezést alakít át Pál</span><span class="sxs-lookup"><span data-stu-id="fc6fb-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="fc6fb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fc6fb-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="fc6fb-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="fc6fb-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="fc6fb-108">`GeneratorIndex` egy PQ kifejezést jelölő kifejezés.</span><span class="sxs-lookup"><span data-stu-id="fc6fb-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="fc6fb-109">Kimenet: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="fc6fb-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="fc6fb-110">A "GeneratorIndex []" kifejezésben a PQ kifejezést Pauli-kifejezésként fejezi ki.</span><span class="sxs-lookup"><span data-stu-id="fc6fb-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>