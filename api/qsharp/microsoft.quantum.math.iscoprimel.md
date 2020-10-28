---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722310"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="fe9f1-102">IsCoprimeL függvény</span><span class="sxs-lookup"><span data-stu-id="fe9f1-102">IsCoprimeL function</span></span>

<span data-ttu-id="fe9f1-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fe9f1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fe9f1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe9f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe9f1-105">Igaz értéket ad vissza, ha a $a $ és a $b $ együttes elsődleges és hamis.</span><span class="sxs-lookup"><span data-stu-id="fe9f1-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="fe9f1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fe9f1-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="fe9f1-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe9f1-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe9f1-108">az első szám, amelynek a közös primality tesztelése folyamatban van</span><span class="sxs-lookup"><span data-stu-id="fe9f1-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="fe9f1-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe9f1-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe9f1-110">a második szám, amelynek a közös primality tesztelve van</span><span class="sxs-lookup"><span data-stu-id="fe9f1-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe9f1-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe9f1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe9f1-112">Igaz, ha a $a $ és a $b $ együttes elsődleges (például a legnagyobb közös osztó értéke 1), máskülönben hamis értéket ad meg.</span><span class="sxs-lookup"><span data-stu-id="fe9f1-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>