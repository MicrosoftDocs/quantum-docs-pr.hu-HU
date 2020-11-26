---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231092"
---
# <a name="integerbits-function"></a><span data-ttu-id="f8e0a-102">IntegerBits függvény</span><span class="sxs-lookup"><span data-stu-id="f8e0a-102">IntegerBits function</span></span>

<span data-ttu-id="f8e0a-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f8e0a-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f8e0a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8e0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8e0a-105">Az összes olyan pozíciót adja vissza, amelyben egy egész számú bit be van állítva.</span><span class="sxs-lookup"><span data-stu-id="f8e0a-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="f8e0a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f8e0a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f8e0a-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8e0a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8e0a-108">Nem negatív szám.</span><span class="sxs-lookup"><span data-stu-id="f8e0a-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="f8e0a-109">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8e0a-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8e0a-110">A bináris kiterjesztésű bitek száma `value` .</span><span class="sxs-lookup"><span data-stu-id="f8e0a-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="f8e0a-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8e0a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8e0a-112">Az összes bitet tartalmazó tömb (0-tól kezdődően), amely a bináris kiterjesztésben 1 az `value` összes bit pozícióig `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="f8e0a-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="f8e0a-113">A tömbben az összes pozíciót növekvő sorrendben rendezi a rendszer.</span><span class="sxs-lookup"><span data-stu-id="f8e0a-113">All positions are ordered in the array by position in an increasing order.</span></span>