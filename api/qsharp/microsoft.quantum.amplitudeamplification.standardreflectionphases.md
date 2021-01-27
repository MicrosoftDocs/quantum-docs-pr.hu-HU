---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843916"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="b71e4-102">StandardReflectionPhases függvény</span><span class="sxs-lookup"><span data-stu-id="b71e4-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="b71e4-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b71e4-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b71e4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b71e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b71e4-105">Kiszámítja a standard amplitúdó-erősítés részleges reflexiós fázisait.</span><span class="sxs-lookup"><span data-stu-id="b71e4-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="b71e4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b71e4-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="b71e4-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b71e4-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b71e4-108">Az amplitúdó-erősítési Ismétlések száma a részleges reflexiós fázisok létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b71e4-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="b71e4-109">Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b71e4-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b71e4-110">A részleges tükrözéseknek megadott fázisokat megvalósító művelet</span><span class="sxs-lookup"><span data-stu-id="b71e4-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="b71e4-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b71e4-111">Remarks</span></span>

<span data-ttu-id="b71e4-112">Az összes fázis a $ \pi $, kivéve a kezdő állapot első tükrözését és a célként megadott állapottal kapcsolatos utolsó tükrözést, amely $0 $.</span><span class="sxs-lookup"><span data-stu-id="b71e4-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>