---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 907e270e1c3710fb346044ad7757171c6d5f568d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223051"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="43e95-102">IdenticalPointPosFactFxP függvény</span><span class="sxs-lookup"><span data-stu-id="43e95-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="43e95-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="43e95-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="43e95-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="43e95-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="43e95-105">Azt állítja be, hogy a megadott tömbben lévő összes rögzített szintű szám azonos ponttal rendelkezik, amikor a legkevésbé jelentős mennyiségtől számít.</span><span class="sxs-lookup"><span data-stu-id="43e95-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="43e95-106">Azaz a BITS mínusz pont pozíciójának állandónak kell lennie a tömbben lévő összes rögzített számnál.</span><span class="sxs-lookup"><span data-stu-id="43e95-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="43e95-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="43e95-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="43e95-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="43e95-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="43e95-109">A kompatibilitáshoz ellenőrizendő kvantum-pontokból álló számok tömbje (kijelentések használata).</span><span class="sxs-lookup"><span data-stu-id="43e95-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="43e95-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="43e95-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

