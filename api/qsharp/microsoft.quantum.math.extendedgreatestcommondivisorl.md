---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723711"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="4943b-102">ExtendedGreatestCommonDivisorL függvény</span><span class="sxs-lookup"><span data-stu-id="4943b-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="4943b-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4943b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4943b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4943b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4943b-105">Kiszámítja az $ (u, v) $ értéket, hogy $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, ahol a $ \operatorname{GCD} $ $a $ Greatest Common osztója $a $ és $b $.</span><span class="sxs-lookup"><span data-stu-id="4943b-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="4943b-106">A GCD mindig pozitív.</span><span class="sxs-lookup"><span data-stu-id="4943b-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="4943b-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4943b-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4943b-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4943b-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4943b-109">az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van</span><span class="sxs-lookup"><span data-stu-id="4943b-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4943b-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4943b-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4943b-111">a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva</span><span class="sxs-lookup"><span data-stu-id="4943b-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="4943b-112">Kimenet: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="4943b-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="4943b-113">Rekord $ (u, v) $, $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $ tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="4943b-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="4943b-114">Referencia</span><span class="sxs-lookup"><span data-stu-id="4943b-114">References</span></span>

- <span data-ttu-id="4943b-115">Ez a megvalósítás a következő szerint https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="4943b-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>