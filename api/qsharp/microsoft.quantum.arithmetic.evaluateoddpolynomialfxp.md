---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 1bf9b6e7c416e994e70b93e5967caefd444f6426
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223221"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="99af1-102">EvaluateOddPolynomialFxP művelet</span><span class="sxs-lookup"><span data-stu-id="99af1-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="99af1-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="99af1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="99af1-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="99af1-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="99af1-105">Kiértékeli a páratlan polinom-t egy rögzített pontos ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="99af1-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="99af1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="99af1-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="99af1-107">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="99af1-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="99af1-108">A páratlan polinom és a kettős tömb együttes hatékonysága, azaz a következő tömb: $ [a_0, a_1,..., a_k] $ a páratlan polinom $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2k + 1} $.</span><span class="sxs-lookup"><span data-stu-id="99af1-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="99af1-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="99af1-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="99af1-110">Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.</span><span class="sxs-lookup"><span data-stu-id="99af1-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="99af1-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="99af1-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="99af1-112">Kimeneti rögzített pont szám, amely a P (x) értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="99af1-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="99af1-113">Kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="99af1-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="99af1-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99af1-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

