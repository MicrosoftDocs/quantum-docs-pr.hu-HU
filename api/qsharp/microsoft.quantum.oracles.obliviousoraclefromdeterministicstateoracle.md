---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722226"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="df062-102">ObliviousOracleFromDeterministicStateOracle függvény</span><span class="sxs-lookup"><span data-stu-id="df062-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="df062-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="df062-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="df062-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df062-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df062-105">Egyesíti az Oracle `DeterministicStateOracle` -ket és a-t `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="df062-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="df062-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df062-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="df062-107">ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="df062-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="df062-108">Olyan állapot-előkészítési Oracle $A $, amely a (z `DeterministicStateOracle` ) $a $ regiszterben működik.</span><span class="sxs-lookup"><span data-stu-id="df062-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="df062-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="df062-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="df062-110">Egy Oracle $U $ típusú, amely `ObliviousOracle` a register $a, s $ címen közösen működik.</span><span class="sxs-lookup"><span data-stu-id="df062-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="df062-111">Kimenet: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="df062-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="df062-112">Egy Oracle $O = UA $ típusú `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="df062-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="df062-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="df062-113">See Also</span></span>

- [<span data-ttu-id="df062-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="df062-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="df062-115">Microsoft. Quantum. Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="df062-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)