---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 7212f918e1d0ee86b12b85caa6e0c27bc2cebe58
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846615"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="d5bc4-102">IdenticalPointPosFactFxP függvény</span><span class="sxs-lookup"><span data-stu-id="d5bc4-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="d5bc4-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d5bc4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d5bc4-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d5bc4-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d5bc4-105">Azt állítja be, hogy a megadott tömbben lévő összes rögzített szintű szám azonos ponttal rendelkezik, amikor a legkevésbé jelentős mennyiségtől számít.</span><span class="sxs-lookup"><span data-stu-id="d5bc4-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="d5bc4-106">Azaz a BITS mínusz pont pozíciójának állandónak kell lennie a tömbben lévő összes rögzített számnál.</span><span class="sxs-lookup"><span data-stu-id="d5bc4-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d5bc4-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d5bc4-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="d5bc4-108">fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="d5bc4-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="d5bc4-109">A kompatibilitáshoz ellenőrizendő kvantum-pontokból álló számok tömbje (kijelentések használata).</span><span class="sxs-lookup"><span data-stu-id="d5bc4-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5bc4-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5bc4-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

