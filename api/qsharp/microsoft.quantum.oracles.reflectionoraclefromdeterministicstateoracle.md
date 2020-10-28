---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722184"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="90e28-102">ReflectionOracleFromDeterministicStateOracle függvény</span><span class="sxs-lookup"><span data-stu-id="90e28-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="90e28-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="90e28-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="90e28-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90e28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90e28-105">Egy Oracle-ből származó adott állapottal kapcsolatos reflexiót hoz létre.</span><span class="sxs-lookup"><span data-stu-id="90e28-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="90e28-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="90e28-106">Description</span></span>

<span data-ttu-id="90e28-107">Mivel a determinisztikus állapot-előkészítési Oracle egy egységes Matrix $O $-t képvisel, a függvény eredménye egy Oracle, amely az Oracle $O $ által előkészített \ket{\psi} $ állapotot tükrözi. vagyis a $ \ket{\psi} $ állapotot, amely $O \ket {0} = \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="90e28-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="90e28-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="90e28-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="90e28-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="90e28-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="90e28-110">Egy Oracle, amely előkészíti a $ \ket{\psi} $ állapotú példányokat.</span><span class="sxs-lookup"><span data-stu-id="90e28-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="90e28-111">Kimenet: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="90e28-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="90e28-112">Egy Oracle, amely a $ \ket{\psi} $ állapotot tükrözi.</span><span class="sxs-lookup"><span data-stu-id="90e28-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="90e28-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="90e28-113">See Also</span></span>

- [<span data-ttu-id="90e28-114">Microsoft. Quantum. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="90e28-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="90e28-115">Microsoft. Quantum. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="90e28-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)