---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721751"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="e7f81-102">RotationPhasesAsReflectionPhases függvény</span><span class="sxs-lookup"><span data-stu-id="e7f81-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="e7f81-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e7f81-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e7f81-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e7f81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e7f81-105">Egy qubit elforgatásként megadott fázisokat alakít át részleges reflexiók megadott fázisokra.</span><span class="sxs-lookup"><span data-stu-id="e7f81-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="e7f81-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e7f81-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="e7f81-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="e7f81-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="e7f81-108">A részleges reflexiók átalakítására szolgáló qubit-forgatások tömbje.</span><span class="sxs-lookup"><span data-stu-id="e7f81-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="e7f81-109">Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="e7f81-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="e7f81-110">Egy művelet, amely a részleges reflexiók által megadott fázisokat implementálja.</span><span class="sxs-lookup"><span data-stu-id="e7f81-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="e7f81-111">Referencia</span><span class="sxs-lookup"><span data-stu-id="e7f81-111">References</span></span>

<span data-ttu-id="e7f81-112">Az egyezményt a</span><span class="sxs-lookup"><span data-stu-id="e7f81-112">We use the convention in</span></span>

- <span data-ttu-id="e7f81-113">[ *G.H. Low, I. L.*](https://arxiv.org/abs/1707.05391) qubit, amely a reflexiós operátori fázisok esetében az egyfázisú rotációs fázisokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="e7f81-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>