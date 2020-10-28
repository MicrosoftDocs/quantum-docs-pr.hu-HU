---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713458"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="9035a-102">IntAsBoolArray függvény</span><span class="sxs-lookup"><span data-stu-id="9035a-102">IntAsBoolArray function</span></span>

<span data-ttu-id="9035a-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="9035a-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="9035a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9035a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9035a-105">Egy pozitív egész szám bináris ábrázolását állítja elő a visszaadott tömb kis endian ábrázolásával.</span><span class="sxs-lookup"><span data-stu-id="9035a-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="9035a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9035a-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="9035a-107">szám: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9035a-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9035a-108">Egy pozitív egész szám, amelyet logikai értékek tömbje alakít át.</span><span class="sxs-lookup"><span data-stu-id="9035a-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="9035a-109">BITS: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9035a-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9035a-110">A bináris ábrázolásban lévő bitek száma `number` .</span><span class="sxs-lookup"><span data-stu-id="9035a-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9035a-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="9035a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="9035a-112">A logikai értékek tömbje, amely a értéket jelképezi `number` .</span><span class="sxs-lookup"><span data-stu-id="9035a-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9035a-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9035a-113">Remarks</span></span>

<span data-ttu-id="9035a-114">A bemenetnek `bits` 0 és 63 közöttinek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9035a-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="9035a-115">A bemenetnek `number` 0 és $2 ^ {\texttt{BITS}}-$1 között kell lennie.</span><span class="sxs-lookup"><span data-stu-id="9035a-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>