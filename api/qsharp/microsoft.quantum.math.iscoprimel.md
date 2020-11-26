---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228134"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="d97a8-102">IsCoprimeL függvény</span><span class="sxs-lookup"><span data-stu-id="d97a8-102">IsCoprimeL function</span></span>

<span data-ttu-id="d97a8-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d97a8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d97a8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d97a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d97a8-105">Igaz értéket ad vissza, ha a $a $ és a $b $ együttes elsődleges és hamis.</span><span class="sxs-lookup"><span data-stu-id="d97a8-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="d97a8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d97a8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="d97a8-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d97a8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d97a8-108">az első szám, amelynek a közös primality tesztelése folyamatban van</span><span class="sxs-lookup"><span data-stu-id="d97a8-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="d97a8-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d97a8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d97a8-110">a második szám, amelynek a közös primality tesztelve van</span><span class="sxs-lookup"><span data-stu-id="d97a8-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="d97a8-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d97a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d97a8-112">Igaz, ha a $a $ és a $b $ együttes elsődleges (például a legnagyobb közös osztó értéke 1), máskülönben hamis értéket ad meg.</span><span class="sxs-lookup"><span data-stu-id="d97a8-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>