---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723724"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="05b00-102">ExtendedGreatestCommonDivisorI függvény</span><span class="sxs-lookup"><span data-stu-id="05b00-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="05b00-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="05b00-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="05b00-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="05b00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="05b00-105">Kiszámítja az $ (u, v) $ értéket, hogy $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, ahol a $ \operatorname{GCD} $ $a $ Greatest Common osztója $a $ és $b $.</span><span class="sxs-lookup"><span data-stu-id="05b00-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="05b00-106">A GCD mindig pozitív.</span><span class="sxs-lookup"><span data-stu-id="05b00-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="05b00-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="05b00-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="05b00-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05b00-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05b00-109">az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van</span><span class="sxs-lookup"><span data-stu-id="05b00-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="05b00-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05b00-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05b00-111">a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva</span><span class="sxs-lookup"><span data-stu-id="05b00-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="05b00-112">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="05b00-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="05b00-113">Rekord $ (u, v) $, $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $ tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="05b00-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="05b00-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="05b00-114">References</span></span>

- <span data-ttu-id="05b00-115">Ez a megvalósítás a következő szerint https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="05b00-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>