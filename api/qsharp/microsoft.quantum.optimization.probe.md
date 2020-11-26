---
uid: Microsoft.Quantum.Optimization.Probe
title: Mintavételi függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: Probe
qsharp.summary: Given an interval, returns a probe interval that contracts the given interval by a factor of the golden ratio.
ms.openlocfilehash: bbb30fcdeb53173ac3a316c60efb698a378089f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226927"
---
# <a name="probe-function"></a><span data-ttu-id="10c5b-102">Mintavételi függvény</span><span class="sxs-lookup"><span data-stu-id="10c5b-102">Probe function</span></span>

<span data-ttu-id="10c5b-103">Névtér: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="10c5b-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="10c5b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="10c5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="10c5b-105">Adott intervallumban egy mintavételi intervallumot ad vissza, amely a megadott intervallumot az arany arány egy tényezője alapján állítja be.</span><span class="sxs-lookup"><span data-stu-id="10c5b-105">Given an interval, returns a probe interval that contracts the given interval by a factor of the golden ratio.</span></span>

```qsharp
function Probe (left : Double, right : Double) : (Double, Double)
```


## <a name="input"></a><span data-ttu-id="10c5b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="10c5b-106">Input</span></span>

### <a name="left--double"></a><span data-ttu-id="10c5b-107">balra: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10c5b-107">left : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="right--double"></a><span data-ttu-id="10c5b-108">jobb: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="10c5b-108">right : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--doubledouble"></a><span data-ttu-id="10c5b-109">Kimenet: ([dupla](xref:microsoft.quantum.lang-ref.double),[dupla](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="10c5b-109">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

