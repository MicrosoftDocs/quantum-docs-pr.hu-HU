---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843964"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="aa2a6-102">RotationPhases-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="aa2a6-102">RotationPhases user defined type</span></span>

<span data-ttu-id="aa2a6-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="aa2a6-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="aa2a6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa2a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa2a6-105">Egy qubit-Forgások sorozatának fázisai az amplitúdó-erősítésben.</span><span class="sxs-lookup"><span data-stu-id="aa2a6-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="aa2a6-106">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="aa2a6-106">Remarks</span></span>

<span data-ttu-id="aa2a6-107">Az első paraméter a reflexiók fázisainak egy tömbje, amely egy qubit-rotációs termékként van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="aa2a6-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="aa2a6-108">[G.H.</span><span class="sxs-lookup"><span data-stu-id="aa2a6-108">[ G.H.</span></span> <span data-ttu-id="aa2a6-109">Alacsony, I. L.</span><span class="sxs-lookup"><span data-stu-id="aa2a6-109">Low, I. L.</span></span> <span data-ttu-id="aa2a6-110">A https://arxiv.org/abs/1707.05391 ...)</span><span class="sxs-lookup"><span data-stu-id="aa2a6-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>