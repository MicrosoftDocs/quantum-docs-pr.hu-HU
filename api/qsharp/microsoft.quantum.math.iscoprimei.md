---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195358"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="73eec-102">IsCoprimeI függvény</span><span class="sxs-lookup"><span data-stu-id="73eec-102">IsCoprimeI function</span></span>

<span data-ttu-id="73eec-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="73eec-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="73eec-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73eec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73eec-105">Igaz értéket ad vissza, ha a $a $ és a $b $ együttes elsődleges és hamis.</span><span class="sxs-lookup"><span data-stu-id="73eec-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="73eec-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="73eec-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="73eec-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="73eec-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="73eec-108">az első szám, amelynek a közös primality tesztelése folyamatban van</span><span class="sxs-lookup"><span data-stu-id="73eec-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="73eec-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="73eec-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="73eec-110">a második szám, amelynek a közös primality tesztelve van</span><span class="sxs-lookup"><span data-stu-id="73eec-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="73eec-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="73eec-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="73eec-112">Igaz, ha a $a $ és a $b $ együttes elsődleges (például a legnagyobb közös osztó értéke 1), máskülönben hamis értéket ad meg.</span><span class="sxs-lookup"><span data-stu-id="73eec-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>