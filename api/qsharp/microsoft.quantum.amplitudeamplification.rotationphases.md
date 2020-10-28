---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721765"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="81f15-102">RotationPhases-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="81f15-102">RotationPhases user defined type</span></span>

<span data-ttu-id="81f15-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="81f15-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="81f15-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81f15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81f15-105">Egy qubit-Forgások sorozatának fázisai az amplitúdó-erősítésben.</span><span class="sxs-lookup"><span data-stu-id="81f15-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="81f15-106">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="81f15-106">Remarks</span></span>

<span data-ttu-id="81f15-107">Az első paraméter a reflexiók fázisainak egy tömbje, amely egy qubit-rotációs termékként van kifejezve.</span><span class="sxs-lookup"><span data-stu-id="81f15-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="81f15-108">[G.H.</span><span class="sxs-lookup"><span data-stu-id="81f15-108">[ G.H.</span></span> <span data-ttu-id="81f15-109">Alacsony, I. L.</span><span class="sxs-lookup"><span data-stu-id="81f15-109">Low, I. L.</span></span> <span data-ttu-id="81f15-110">A https://arxiv.org/abs/1707.05391 ...)</span><span class="sxs-lookup"><span data-stu-id="81f15-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>