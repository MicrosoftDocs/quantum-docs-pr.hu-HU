---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 7fd891aa2e4753020ec9ac4e702f8af9edc9df0a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723654"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="d6e61-102">GreatestCommonDivisorI függvény</span><span class="sxs-lookup"><span data-stu-id="d6e61-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="d6e61-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d6e61-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d6e61-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6e61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6e61-105">Kiszámítja $a $ és $b $ közötti legnagyobb közös osztót.</span><span class="sxs-lookup"><span data-stu-id="d6e61-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="d6e61-106">A GCD mindig pozitív.</span><span class="sxs-lookup"><span data-stu-id="d6e61-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d6e61-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d6e61-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d6e61-108">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6e61-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6e61-109">az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van</span><span class="sxs-lookup"><span data-stu-id="d6e61-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="d6e61-110">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6e61-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6e61-111">a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva</span><span class="sxs-lookup"><span data-stu-id="d6e61-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="d6e61-112">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d6e61-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d6e61-113">$a $ és $b $ legnagyobb közös osztója</span><span class="sxs-lookup"><span data-stu-id="d6e61-113">Greatest common divisor of $a$ and $b$</span></span>