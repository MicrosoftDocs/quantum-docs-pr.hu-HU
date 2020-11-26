---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224343"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="6706e-102">IntAsBoolArray függvény</span><span class="sxs-lookup"><span data-stu-id="6706e-102">IntAsBoolArray function</span></span>

<span data-ttu-id="6706e-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="6706e-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="6706e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6706e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6706e-105">Egy pozitív egész szám bináris ábrázolását állítja elő a visszaadott tömb kis endian ábrázolásával.</span><span class="sxs-lookup"><span data-stu-id="6706e-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="6706e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6706e-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="6706e-107">szám: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6706e-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6706e-108">Egy pozitív egész szám, amelyet logikai értékek tömbje alakít át.</span><span class="sxs-lookup"><span data-stu-id="6706e-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="6706e-109">BITS: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6706e-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6706e-110">A bináris ábrázolásban lévő bitek száma `number` .</span><span class="sxs-lookup"><span data-stu-id="6706e-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6706e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6706e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6706e-112">A logikai értékek tömbje, amely a értéket jelképezi `number` .</span><span class="sxs-lookup"><span data-stu-id="6706e-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6706e-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6706e-113">Remarks</span></span>

<span data-ttu-id="6706e-114">A bemenetnek `bits` 0 és 63 közöttinek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6706e-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="6706e-115">A bemenetnek `number` 0 és $2 ^ {\texttt{BITS}}-$1 között kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6706e-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>