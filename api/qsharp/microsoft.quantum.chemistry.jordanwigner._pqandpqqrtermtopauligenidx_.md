---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _PQandPQQRTermToPauliGenIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 17acd2c09129275af90222e30fd96a7551e18b50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203535"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="5e369-102">_PQandPQQRTermToPauliGenIdx_ függvény</span><span class="sxs-lookup"><span data-stu-id="5e369-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="5e369-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5e369-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5e369-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5e369-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5e369-105">Egy PQ vagy PQQR kifejezést leíró GeneratorIndex alakít át a (z) "GeneratorIndex []" kifejezésre Paulis alapján</span><span class="sxs-lookup"><span data-stu-id="5e369-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="5e369-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e369-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="5e369-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="5e369-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="5e369-108">`GeneratorIndex` PQ vagy PQQR kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="5e369-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="5e369-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="5e369-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="5e369-110">A "GeneratorIndex []" a PQ vagy a PQQR kifejezést Pauli-kifejezésként fejezi ki.</span><span class="sxs-lookup"><span data-stu-id="5e369-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>