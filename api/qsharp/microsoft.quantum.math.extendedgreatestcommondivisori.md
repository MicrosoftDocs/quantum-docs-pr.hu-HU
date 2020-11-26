---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195527"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="b26ea-102">ExtendedGreatestCommonDivisorI függvény</span><span class="sxs-lookup"><span data-stu-id="b26ea-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="b26ea-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b26ea-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b26ea-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b26ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b26ea-105">Kiszámítja az $ (u, v) $ értéket, hogy $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, ahol a $ \operatorname{GCD} $ $a $ Greatest Common osztója $a $ és $b $.</span><span class="sxs-lookup"><span data-stu-id="b26ea-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="b26ea-106">A GCD mindig pozitív.</span><span class="sxs-lookup"><span data-stu-id="b26ea-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="b26ea-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b26ea-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b26ea-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b26ea-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b26ea-109">az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van</span><span class="sxs-lookup"><span data-stu-id="b26ea-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="b26ea-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b26ea-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b26ea-111">a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva</span><span class="sxs-lookup"><span data-stu-id="b26ea-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="b26ea-112">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="b26ea-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="b26ea-113">Rekord $ (u, v) $, $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $ tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="b26ea-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="b26ea-114">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="b26ea-114">References</span></span>

- <span data-ttu-id="b26ea-115">Ez a megvalósítás a következő szerint https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="b26ea-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>