---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721120"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="c6010-102">IdenticalPointPosFactFxP függvény</span><span class="sxs-lookup"><span data-stu-id="c6010-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="c6010-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c6010-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c6010-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6010-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6010-105">Azt állítja be, hogy a megadott tömbben lévő összes rögzített szintű szám azonos ponttal rendelkezik, amikor a legkevésbé jelentős mennyiségtől számít.</span><span class="sxs-lookup"><span data-stu-id="c6010-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="c6010-106">Azaz a BITS mínusz pont pozíciójának állandónak kell lennie a tömbben lévő összes rögzített számnál.</span><span class="sxs-lookup"><span data-stu-id="c6010-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c6010-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c6010-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="c6010-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="c6010-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="c6010-109">A kompatibilitáshoz ellenőrizendő kvantum-pontokból álló számok tömbje (kijelentések használata).</span><span class="sxs-lookup"><span data-stu-id="c6010-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6010-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6010-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

