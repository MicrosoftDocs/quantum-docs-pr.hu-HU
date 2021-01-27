---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843053"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="c40a9-102">MultiplyFxP művelet</span><span class="sxs-lookup"><span data-stu-id="c40a9-102">MultiplyFxP operation</span></span>

<span data-ttu-id="c40a9-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c40a9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c40a9-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c40a9-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c40a9-105">A kvantum-regiszterekben két rögzített pontú számot szoroz.</span><span class="sxs-lookup"><span data-stu-id="c40a9-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c40a9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c40a9-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="c40a9-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c40a9-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c40a9-108">Első rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="c40a9-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="c40a9-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c40a9-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c40a9-110">Második rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="c40a9-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="c40a9-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c40a9-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c40a9-112">Az eredmény rögzített pontjának számának kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="c40a9-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c40a9-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c40a9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c40a9-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c40a9-114">Remarks</span></span>

<span data-ttu-id="c40a9-115">A jelenlegi megvalósításhoz a három rögzített pontból álló számnak ugyanazzal a ponttal kell rendelkeznie, és ugyanannyi qubits kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c40a9-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>