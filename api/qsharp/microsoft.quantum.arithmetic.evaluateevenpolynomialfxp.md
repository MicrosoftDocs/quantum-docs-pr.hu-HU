---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843234"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="4f3d9-102">EvaluateEvenPolynomialFxP művelet</span><span class="sxs-lookup"><span data-stu-id="4f3d9-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="4f3d9-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4f3d9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4f3d9-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4f3d9-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4f3d9-105">Kiértékeli a páros polinom-t egy rögzített pontos ábrázolásban.</span><span class="sxs-lookup"><span data-stu-id="4f3d9-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f3d9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4f3d9-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="4f3d9-107">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4f3d9-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4f3d9-108">A páros polinom egyfajta együtthatója kettős tömbként, azaz a következő tömbben: $ [a_0, a_1,..., a_k] $ a páros polinom $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2k} $.</span><span class="sxs-lookup"><span data-stu-id="4f3d9-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="4f3d9-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4f3d9-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4f3d9-110">Bemeneti rögzített pont száma, amelynek kiértékeléséhez a polinom szükséges.</span><span class="sxs-lookup"><span data-stu-id="4f3d9-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="4f3d9-111">eredmény: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4f3d9-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4f3d9-112">Kimeneti rögzített pont száma, amely $P (x) $ értéket fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="4f3d9-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="4f3d9-113">Kezdetben a $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="4f3d9-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f3d9-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f3d9-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

