---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719777"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="d932b-102">MultiplyFxP művelet</span><span class="sxs-lookup"><span data-stu-id="d932b-102">MultiplyFxP operation</span></span>

<span data-ttu-id="d932b-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d932b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d932b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d932b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d932b-105">A kvantum-regiszterekben két rögzített pontú számot szoroz.</span><span class="sxs-lookup"><span data-stu-id="d932b-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="d932b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d932b-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="d932b-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d932b-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d932b-108">Első rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="d932b-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="d932b-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d932b-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d932b-110">Második rögzített pont száma</span><span class="sxs-lookup"><span data-stu-id="d932b-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="d932b-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d932b-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d932b-112">Az eredmény rögzített pontjának számának kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="d932b-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d932b-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d932b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d932b-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d932b-114">Remarks</span></span>

<span data-ttu-id="d932b-115">A jelenlegi megvalósításhoz a három rögzített pontból álló számnak ugyanazzal a ponttal kell rendelkeznie, és ugyanannyi qubits kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d932b-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>