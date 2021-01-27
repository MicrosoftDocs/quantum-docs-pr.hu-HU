---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843246"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="df5e6-102">ComputeReciprocalFxP művelet</span><span class="sxs-lookup"><span data-stu-id="df5e6-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="df5e6-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="df5e6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="df5e6-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="df5e6-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="df5e6-105">Kiszámítja a $1/x $ értéket egy rögzített pont $x $ értékű számra.</span><span class="sxs-lookup"><span data-stu-id="df5e6-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="df5e6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df5e6-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="df5e6-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="df5e6-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="df5e6-108">A rögzített pont számának invertálása.</span><span class="sxs-lookup"><span data-stu-id="df5e6-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="df5e6-109">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="df5e6-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="df5e6-110">Az eredményt tároló rögzített pont száma.</span><span class="sxs-lookup"><span data-stu-id="df5e6-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="df5e6-111">A $ \ket{0.0} $ értékre kell inicializálni.</span><span class="sxs-lookup"><span data-stu-id="df5e6-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df5e6-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df5e6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

