---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: d37bf1c10899d06e798d29c68f88b06f2d5918a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195562"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="898ee-102">ContinuedFractionConvergentI függvény</span><span class="sxs-lookup"><span data-stu-id="898ee-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="898ee-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="898ee-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="898ee-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="898ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="898ee-105">Megkeresi a legközelebb `fraction` lévő, kisebb vagy egyenlő nevezőből álló nevezőt `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="898ee-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="898ee-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="898ee-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="898ee-107">frakció: [frakció](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="898ee-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="898ee-108">denominatorBound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="898ee-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="898ee-109">Kimenet: [töredék](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="898ee-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="898ee-110">A legközelebb `fraction` álló nevező a nevezőnél kisebb vagy egyenlő `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="898ee-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>