---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191108"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="06c85-102">TargetStateReflectionOracle függvény</span><span class="sxs-lookup"><span data-stu-id="06c85-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="06c85-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="06c85-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="06c85-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06c85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06c85-105">A `ReflectionOracle` megcélzott állapotot a jelző qubit egyedileg megjelölve hozza létre.</span><span class="sxs-lookup"><span data-stu-id="06c85-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="06c85-106">A célként megadott állapot egyetlen qubit van beállítva, és az összes többi 0: $ \ket {1} _f $.</span><span class="sxs-lookup"><span data-stu-id="06c85-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="06c85-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="06c85-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="06c85-108">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06c85-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06c85-109">Az Oracle $f $ qubit jelző index.</span><span class="sxs-lookup"><span data-stu-id="06c85-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="06c85-110">Kimenet: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="06c85-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="06c85-111">A `ReflectionOracle` , amely a $ \ket _f $ által jelölt állapotot tükrözi {1} .</span><span class="sxs-lookup"><span data-stu-id="06c85-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="06c85-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="06c85-112">See Also</span></span>

- [<span data-ttu-id="06c85-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="06c85-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)