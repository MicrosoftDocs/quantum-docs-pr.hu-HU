---
uid: Microsoft.Quantum.Math.ModulusL
title: Modulus függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725097"
---
# <a name="modulusl-function"></a><span data-ttu-id="43376-102">Modulus függvény</span><span class="sxs-lookup"><span data-stu-id="43376-102">ModulusL function</span></span>

<span data-ttu-id="43376-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="43376-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="43376-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43376-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43376-105">Kiszámítja a többrészes adatmennyiség kanonikus maradékát `value` `modulus` .</span><span class="sxs-lookup"><span data-stu-id="43376-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="43376-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="43376-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="43376-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="43376-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="43376-108">A maradék kiszámításának értéke</span><span class="sxs-lookup"><span data-stu-id="43376-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="43376-109">modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="43376-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="43376-110">A maradékok által elvégezhető modulusnak pozitívnak kell lennie</span><span class="sxs-lookup"><span data-stu-id="43376-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="43376-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="43376-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="43376-112">Egész szám $r $0 és között, `modulus - 1` amely a `value - r` modulus alapján osztható</span><span class="sxs-lookup"><span data-stu-id="43376-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="43376-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="43376-113">Remarks</span></span>

<span data-ttu-id="43376-114">Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig egy 0 és közötti pozitív egész szám `modulus - 1` , még akkor is, ha az érték negatív.</span><span class="sxs-lookup"><span data-stu-id="43376-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a positive integer between 0 and `modulus - 1`, even if value is negative.</span></span>