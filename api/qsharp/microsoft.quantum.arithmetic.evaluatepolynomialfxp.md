---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 4f6ed4b34af2e63dd8ee31fb9b93119e06e3ecbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223187"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="5e132-102">EvaluatePolynomialFxP művelet</span><span class="sxs-lookup"><span data-stu-id="5e132-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="5e132-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5e132-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5e132-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5e132-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5e132-105">A polinom kiértékelése rögzített pontú ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="5e132-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5e132-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e132-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="5e132-107">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5e132-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5e132-108">A polinom és a kettős tömb együttes hatékonysága, azaz a következő tömb: $ [a_0, a_1,..., a_d] $ a polinom $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="5e132-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="5e132-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5e132-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5e132-110">Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.</span><span class="sxs-lookup"><span data-stu-id="5e132-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="5e132-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="5e132-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="5e132-112">Kimeneti rögzített pont száma, amely $P (x) $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="5e132-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="5e132-113">Kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="5e132-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e132-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e132-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

