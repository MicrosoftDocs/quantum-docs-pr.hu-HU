---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223391"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="10774-102">ComputeReciprocalFxP művelet</span><span class="sxs-lookup"><span data-stu-id="10774-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="10774-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="10774-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="10774-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="10774-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="10774-105">Kiszámítja a $1/x $ értéket egy rögzített pont $x $ értékű számra.</span><span class="sxs-lookup"><span data-stu-id="10774-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="10774-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="10774-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="10774-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="10774-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="10774-108">A rögzített pont számának invertálása.</span><span class="sxs-lookup"><span data-stu-id="10774-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="10774-109">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="10774-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="10774-110">Az eredményt tároló rögzített pont száma.</span><span class="sxs-lookup"><span data-stu-id="10774-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="10774-111">A $ \ket{0.0} $ értékre kell inicializálni.</span><span class="sxs-lookup"><span data-stu-id="10774-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="10774-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="10774-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

