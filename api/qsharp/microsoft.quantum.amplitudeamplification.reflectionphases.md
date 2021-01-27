---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847181"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="a60bb-102">ReflectionPhases-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="a60bb-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="a60bb-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a60bb-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a60bb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a60bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a60bb-105">Az amplitúdó-erősítésben bekövetkező részleges reflexiók sorozatából álló fázisok.</span><span class="sxs-lookup"><span data-stu-id="a60bb-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="a60bb-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="a60bb-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="a60bb-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a60bb-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a60bb-108">Fázisok tömbje az indítási állapottal kapcsolatos reflexióhoz.</span><span class="sxs-lookup"><span data-stu-id="a60bb-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="a60bb-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a60bb-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a60bb-110">Fázisok tömbje a cél állapotának tükrözéséhez.</span><span class="sxs-lookup"><span data-stu-id="a60bb-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="a60bb-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a60bb-111">Remarks</span></span>

<span data-ttu-id="a60bb-112">Mindkét tömbnek egyenlő hosszúságú kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a60bb-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="a60bb-113">Vegye figyelembe, hogy sok esetben a kezdeti állapot és az utolsó fázis a megcélzott állapottal kapcsolatos első fázisa globális fázis-eltolást mutat be, és $0 $ értékre állítható be.</span><span class="sxs-lookup"><span data-stu-id="a60bb-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>