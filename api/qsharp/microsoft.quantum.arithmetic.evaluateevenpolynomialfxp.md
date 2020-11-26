---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: 21c700ccb2b87b906fc4d8b65eddf962353948c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223255"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="ae576-102">EvaluateEvenPolynomialFxP művelet</span><span class="sxs-lookup"><span data-stu-id="ae576-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="ae576-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ae576-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ae576-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="ae576-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="ae576-105">Kiértékeli a páros polinom-t egy rögzített pontos ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="ae576-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ae576-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ae576-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="ae576-107">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ae576-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ae576-108">A páros polinom egyfajta együtthatója kettős tömbként, azaz a következő tömbben: $ [a_0, a_1,..., a_k] $ a páros polinom $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.</span><span class="sxs-lookup"><span data-stu-id="ae576-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="ae576-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ae576-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ae576-110">Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.</span><span class="sxs-lookup"><span data-stu-id="ae576-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="ae576-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="ae576-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="ae576-112">Kimeneti rögzített pont száma, amely $P (x) $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="ae576-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="ae576-113">Kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="ae576-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ae576-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ae576-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

