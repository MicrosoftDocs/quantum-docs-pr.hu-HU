---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723094"
---
# <a name="modulusi-function"></a><span data-ttu-id="a649f-102">ModulusI függvény</span><span class="sxs-lookup"><span data-stu-id="a649f-102">ModulusI function</span></span>

<span data-ttu-id="a649f-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a649f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a649f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a649f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a649f-105">Kiszámítja a többrészes adatmennyiség kanonikus maradékát `value` `modulus` .</span><span class="sxs-lookup"><span data-stu-id="a649f-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a649f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a649f-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="a649f-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a649f-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a649f-108">A maradék kiszámításának értéke</span><span class="sxs-lookup"><span data-stu-id="a649f-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="a649f-109">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a649f-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a649f-110">A maradékok által elvégezhető modulusnak pozitívnak kell lennie</span><span class="sxs-lookup"><span data-stu-id="a649f-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="a649f-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a649f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a649f-112">Egész szám $r $0 és között, `modulus - 1` amely a `value - r` modulus alapján osztható</span><span class="sxs-lookup"><span data-stu-id="a649f-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="a649f-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a649f-113">Remarks</span></span>

<span data-ttu-id="a649f-114">Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig egy 0 és közötti pozitív egész szám `modulus - 1` , még akkor is, ha az érték negatív.</span><span class="sxs-lookup"><span data-stu-id="a649f-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>