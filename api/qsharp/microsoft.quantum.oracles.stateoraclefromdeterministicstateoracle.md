---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724215"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="ed950-102">StateOracleFromDeterministicStateOracle függvény</span><span class="sxs-lookup"><span data-stu-id="ed950-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="ed950-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ed950-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ed950-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed950-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed950-105">Egy típusú Oracle `DeterministicStateOracle` -t konvertál `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="ed950-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="ed950-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ed950-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="ed950-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="ed950-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="ed950-108">Állapot-előkészítési Oracle $A $ típusú `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="ed950-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="ed950-109">Kimenet: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="ed950-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="ed950-110">Ugyanez az állapot-előkészítési Oracle $A $, de mostantól típusa `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="ed950-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="ed950-111">Vegye figyelembe, hogy a jelölő indexe `StateOracle` egy dummy változó, és nincs hatása.</span><span class="sxs-lookup"><span data-stu-id="ed950-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed950-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ed950-112">See Also</span></span>

- [<span data-ttu-id="ed950-113">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="ed950-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="ed950-114">Microsoft. Quantum. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="ed950-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)