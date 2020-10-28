---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721723"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="5f92e-102">TargetStateReflectionOracle függvény</span><span class="sxs-lookup"><span data-stu-id="5f92e-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="5f92e-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="5f92e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="5f92e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f92e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f92e-105">A `ReflectionOracle` megcélzott állapotot a jelző qubit egyedileg megjelölve hozza létre.</span><span class="sxs-lookup"><span data-stu-id="5f92e-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="5f92e-106">A célként megadott állapot egyetlen qubit van beállítva, és az összes többi 0: $ \ket {1} _f $.</span><span class="sxs-lookup"><span data-stu-id="5f92e-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="5f92e-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5f92e-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="5f92e-108">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5f92e-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5f92e-109">Az Oracle $f $ qubit jelző index.</span><span class="sxs-lookup"><span data-stu-id="5f92e-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="5f92e-110">Kimenet: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="5f92e-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="5f92e-111">A `ReflectionOracle` , amely a $ \ket _f $ által jelölt állapotot tükrözi {1} .</span><span class="sxs-lookup"><span data-stu-id="5f92e-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f92e-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="5f92e-112">See Also</span></span>

- [<span data-ttu-id="5f92e-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="5f92e-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)