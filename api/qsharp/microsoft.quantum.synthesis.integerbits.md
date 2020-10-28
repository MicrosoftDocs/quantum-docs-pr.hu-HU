---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719848"
---
# <a name="integerbits-function"></a><span data-ttu-id="ab42c-102">IntegerBits függvény</span><span class="sxs-lookup"><span data-stu-id="ab42c-102">IntegerBits function</span></span>

<span data-ttu-id="ab42c-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ab42c-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ab42c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab42c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab42c-105">Az összes olyan pozíciót adja vissza, amelyben egy egész számú bit be van állítva.</span><span class="sxs-lookup"><span data-stu-id="ab42c-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="ab42c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ab42c-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="ab42c-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab42c-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab42c-108">Nem negatív szám.</span><span class="sxs-lookup"><span data-stu-id="ab42c-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="ab42c-109">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab42c-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab42c-110">A bináris kiterjesztésű bitek száma `value` .</span><span class="sxs-lookup"><span data-stu-id="ab42c-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ab42c-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ab42c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ab42c-112">Az összes bitet tartalmazó tömb (0-tól kezdődően), amely a bináris kiterjesztésben 1 az `value` összes bit pozícióig `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="ab42c-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="ab42c-113">A tömbben az összes pozíciót növekvő sorrendben rendezi a rendszer.</span><span class="sxs-lookup"><span data-stu-id="ab42c-113">All positions are ordered in the array by position in an increasing order.</span></span>