---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191193"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="3fbf0-102">RotationPhasesAsReflectionPhases függvény</span><span class="sxs-lookup"><span data-stu-id="3fbf0-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="3fbf0-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3fbf0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3fbf0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fbf0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fbf0-105">Egy qubit elforgatásként megadott fázisokat alakít át részleges reflexiók megadott fázisokra.</span><span class="sxs-lookup"><span data-stu-id="3fbf0-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="3fbf0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3fbf0-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="3fbf0-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="3fbf0-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="3fbf0-108">A részleges reflexiók átalakítására szolgáló qubit-forgatások tömbje.</span><span class="sxs-lookup"><span data-stu-id="3fbf0-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="3fbf0-109">Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="3fbf0-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="3fbf0-110">Egy művelet, amely a részleges reflexiók által megadott fázisokat implementálja.</span><span class="sxs-lookup"><span data-stu-id="3fbf0-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="3fbf0-111">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="3fbf0-111">References</span></span>

<span data-ttu-id="3fbf0-112">Az egyezményt a</span><span class="sxs-lookup"><span data-stu-id="3fbf0-112">We use the convention in</span></span>

- <span data-ttu-id="3fbf0-113">[ *G.H. Low, I. L.*](https://arxiv.org/abs/1707.05391) qubit, amely a reflexiós operátori fázisok esetében az egyfázisú rotációs fázisokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="3fbf0-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>