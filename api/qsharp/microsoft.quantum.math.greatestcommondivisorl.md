---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723641"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="1b4f6-102">GreatestCommonDivisorL függvény</span><span class="sxs-lookup"><span data-stu-id="1b4f6-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="1b4f6-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1b4f6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1b4f6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b4f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b4f6-105">Kiszámítja $a $ és $b $ közötti legnagyobb közös osztót.</span><span class="sxs-lookup"><span data-stu-id="1b4f6-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="1b4f6-106">A GCD mindig pozitív.</span><span class="sxs-lookup"><span data-stu-id="1b4f6-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="1b4f6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1b4f6-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1b4f6-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b4f6-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b4f6-109">az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van</span><span class="sxs-lookup"><span data-stu-id="1b4f6-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="1b4f6-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b4f6-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b4f6-111">a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva</span><span class="sxs-lookup"><span data-stu-id="1b4f6-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1b4f6-112">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1b4f6-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1b4f6-113">$a $ és $b $ legnagyobb közös osztója</span><span class="sxs-lookup"><span data-stu-id="1b4f6-113">Greatest common divisor of $a$ and $b$</span></span>