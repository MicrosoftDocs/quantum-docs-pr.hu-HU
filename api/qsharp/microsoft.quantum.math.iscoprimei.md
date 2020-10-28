---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723360"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="3b10b-102">IsCoprimeI függvény</span><span class="sxs-lookup"><span data-stu-id="3b10b-102">IsCoprimeI function</span></span>

<span data-ttu-id="3b10b-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3b10b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3b10b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b10b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b10b-105">Igaz értéket ad vissza, ha a $a $ és a $b $ együttes elsődleges és hamis.</span><span class="sxs-lookup"><span data-stu-id="3b10b-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="3b10b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3b10b-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="3b10b-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b10b-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b10b-108">az első szám, amelynek a közös primality tesztelése folyamatban van</span><span class="sxs-lookup"><span data-stu-id="3b10b-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="3b10b-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b10b-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b10b-110">a második szám, amelynek a közös primality tesztelve van</span><span class="sxs-lookup"><span data-stu-id="3b10b-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="3b10b-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3b10b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3b10b-112">Igaz, ha a $a $ és a $b $ együttes elsődleges (például a legnagyobb közös osztó értéke 1), máskülönben hamis értéket ad meg.</span><span class="sxs-lookup"><span data-stu-id="3b10b-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>