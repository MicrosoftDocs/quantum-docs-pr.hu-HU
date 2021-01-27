---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843955"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="97aa5-102">RotationPhasesAsReflectionPhases függvény</span><span class="sxs-lookup"><span data-stu-id="97aa5-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="97aa5-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="97aa5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="97aa5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97aa5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97aa5-105">Egy qubit elforgatásként megadott fázisokat alakít át részleges reflexiók megadott fázisokra.</span><span class="sxs-lookup"><span data-stu-id="97aa5-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="97aa5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="97aa5-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="97aa5-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="97aa5-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="97aa5-108">A részleges reflexiók átalakítására szolgáló qubit-forgatások tömbje.</span><span class="sxs-lookup"><span data-stu-id="97aa5-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="97aa5-109">Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="97aa5-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="97aa5-110">Egy művelet, amely a részleges reflexiók által megadott fázisokat implementálja.</span><span class="sxs-lookup"><span data-stu-id="97aa5-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="97aa5-111">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="97aa5-111">References</span></span>

<span data-ttu-id="97aa5-112">Az egyezményt a</span><span class="sxs-lookup"><span data-stu-id="97aa5-112">We use the convention in</span></span>

- <span data-ttu-id="97aa5-113">[ *G.H. Low, I. L.*](https://arxiv.org/abs/1707.05391) qubit, amely a reflexiós operátori fázisok esetében az egyfázisú rotációs fázisokra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="97aa5-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>