---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227777"
---
# <a name="modulusi-function"></a><span data-ttu-id="25e5b-102">ModulusI függvény</span><span class="sxs-lookup"><span data-stu-id="25e5b-102">ModulusI function</span></span>

<span data-ttu-id="25e5b-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="25e5b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="25e5b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25e5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25e5b-105">Kiszámítja a többrészes adatmennyiség kanonikus maradékát `value` `modulus` .</span><span class="sxs-lookup"><span data-stu-id="25e5b-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="25e5b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="25e5b-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="25e5b-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25e5b-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25e5b-108">A maradék kiszámításának értéke</span><span class="sxs-lookup"><span data-stu-id="25e5b-108">The value of which residue is computed</span></span>


### <a name="modulus--int"></a><span data-ttu-id="25e5b-109">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25e5b-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25e5b-110">A maradékok által elvégezhető modulusnak pozitívnak kell lennie</span><span class="sxs-lookup"><span data-stu-id="25e5b-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--int"></a><span data-ttu-id="25e5b-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="25e5b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="25e5b-112">Egész szám $r $0 és között, `modulus - 1` amely a `value - r` modulus alapján osztható</span><span class="sxs-lookup"><span data-stu-id="25e5b-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="25e5b-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="25e5b-113">Remarks</span></span>

<span data-ttu-id="25e5b-114">Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig egy 0 és közötti pozitív egész szám `modulus - 1` , még akkor is, ha az érték negatív.</span><span class="sxs-lookup"><span data-stu-id="25e5b-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>