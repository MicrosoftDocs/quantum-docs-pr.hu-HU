---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222609"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="22a5e-102">MultiplyFxP művelet</span><span class="sxs-lookup"><span data-stu-id="22a5e-102">MultiplyFxP operation</span></span>

<span data-ttu-id="22a5e-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="22a5e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="22a5e-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="22a5e-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="22a5e-105">A kvantum-regiszterekben két rögzített pontú számot szoroz.</span><span class="sxs-lookup"><span data-stu-id="22a5e-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="22a5e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="22a5e-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="22a5e-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="22a5e-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="22a5e-108">Első rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="22a5e-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="22a5e-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="22a5e-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="22a5e-110">Második rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="22a5e-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="22a5e-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="22a5e-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="22a5e-112">Az eredmény rögzített pontjának számának kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="22a5e-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="22a5e-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="22a5e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="22a5e-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="22a5e-114">Remarks</span></span>

<span data-ttu-id="22a5e-115">A jelenlegi megvalósításhoz a három rögzített pontból álló számnak ugyanazzal a ponttal kell rendelkeznie, és ugyanannyi qubits kell lennie.</span><span class="sxs-lookup"><span data-stu-id="22a5e-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>