---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 2322e005a5afb73d9719eb65d9ebf50740f1c9fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723179"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="a9a51-102">ContinuedFractionConvergentI függvény</span><span class="sxs-lookup"><span data-stu-id="a9a51-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="a9a51-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a9a51-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a9a51-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9a51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9a51-105">Megkeresi a legközelebb `fraction` lévő, kisebb vagy egyenlő nevezőből álló nevezőt `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="a9a51-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="a9a51-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a9a51-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="a9a51-107">frakció: [frakció](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="a9a51-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="a9a51-108">denominatorBound: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a9a51-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="a9a51-109">Kimenet: [töredék](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="a9a51-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="a9a51-110">A legközelebb `fraction` álló nevező a nevezőnél kisebb vagy egyenlő `denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="a9a51-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>