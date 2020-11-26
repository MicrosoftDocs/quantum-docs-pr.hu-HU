---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193811"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="14f60-102">StateOracleFromDeterministicStateOracle függvény</span><span class="sxs-lookup"><span data-stu-id="14f60-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="14f60-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="14f60-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="14f60-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14f60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14f60-105">Egy típusú Oracle `DeterministicStateOracle` -t konvertál `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="14f60-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="14f60-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="14f60-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="14f60-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="14f60-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="14f60-108">Állapot-előkészítési Oracle $A $ típusú `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="14f60-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="14f60-109">Kimenet: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="14f60-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="14f60-110">Ugyanez az állapot-előkészítési Oracle $A $, de mostantól típusa `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="14f60-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="14f60-111">Vegye figyelembe, hogy a jelölő indexe `StateOracle` egy dummy változó, és nincs hatása.</span><span class="sxs-lookup"><span data-stu-id="14f60-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="14f60-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="14f60-112">See Also</span></span>

- [<span data-ttu-id="14f60-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="14f60-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="14f60-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="14f60-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)