---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191363"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="f39d9-102">RotationPhases-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="f39d9-102">RotationPhases user defined type</span></span>

<span data-ttu-id="f39d9-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="f39d9-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="f39d9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f39d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f39d9-105">Egy qubit-Forgások sorozatának fázisai az amplitúdó-erősítésben.</span><span class="sxs-lookup"><span data-stu-id="f39d9-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="f39d9-106">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f39d9-106">Remarks</span></span>

<span data-ttu-id="f39d9-107">Az első paraméter a reflexiók fázisainak egy tömbje, amely egy qubit-rotációs termékként van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="f39d9-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="f39d9-108">[G.H.</span><span class="sxs-lookup"><span data-stu-id="f39d9-108">[ G.H.</span></span> <span data-ttu-id="f39d9-109">Alacsony, I. L.</span><span class="sxs-lookup"><span data-stu-id="f39d9-109">Low, I. L.</span></span> <span data-ttu-id="f39d9-110">A https://arxiv.org/abs/1707.05391 ...)</span><span class="sxs-lookup"><span data-stu-id="f39d9-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>