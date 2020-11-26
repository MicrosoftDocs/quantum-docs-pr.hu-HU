---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191448"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="16348-102">FixedPointReflectionPhases függvény</span><span class="sxs-lookup"><span data-stu-id="16348-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="16348-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="16348-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="16348-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16348-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16348-105">Kiszámítja a rögzített pont amplitúdó-erősítésének részleges reflexiós fázisait.</span><span class="sxs-lookup"><span data-stu-id="16348-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="16348-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="16348-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="16348-107">nQueries: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="16348-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="16348-108">Az állapot-előkészítési Oracle-nek küldött lekérdezések száma.</span><span class="sxs-lookup"><span data-stu-id="16348-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="16348-109">Páratlan egész számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="16348-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="16348-110">successMin: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="16348-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="16348-111">A cél minimális sikerességének valószínűsége.</span><span class="sxs-lookup"><span data-stu-id="16348-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="16348-112">Kimenet: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="16348-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="16348-113">Fázisok tömbje, amelyek felhasználhatók a rögzített pont amplitúdó-erősítési kvantum-algoritmus megvalósításában.</span><span class="sxs-lookup"><span data-stu-id="16348-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="16348-114">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="16348-114">References</span></span>

<span data-ttu-id="16348-115">A "rögzített pontú amplitúdó-erősítés" fázisait a lekérdezések optimális számával használjuk.</span><span class="sxs-lookup"><span data-stu-id="16348-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="16348-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Lásd még: "összetett kvantum-kapuk módszertana"</span><span class="sxs-lookup"><span data-stu-id="16348-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="16348-117">A fázisok [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) a következő `RotationPhases` formátumban:.</span><span class="sxs-lookup"><span data-stu-id="16348-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>