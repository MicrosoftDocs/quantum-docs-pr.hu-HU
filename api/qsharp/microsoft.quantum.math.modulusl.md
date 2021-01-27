---
uid: Microsoft.Quantum.Math.ModulusL
title: Modulus függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842747"
---
# <a name="modulusl-function"></a><span data-ttu-id="3014c-102">Modulus függvény</span><span class="sxs-lookup"><span data-stu-id="3014c-102">ModulusL function</span></span>

<span data-ttu-id="3014c-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="3014c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="3014c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3014c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3014c-105">Kiszámítja a többrészes adatmennyiség kanonikus maradékát `value` `modulus` .</span><span class="sxs-lookup"><span data-stu-id="3014c-105">Computes the canonical residue of `value` modulo `modulus`.</span></span>

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="3014c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3014c-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="3014c-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3014c-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3014c-108">A maradék kiszámításának értéke</span><span class="sxs-lookup"><span data-stu-id="3014c-108">The value of which residue is computed</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="3014c-109">modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3014c-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3014c-110">A maradékok által elvégezhető modulusnak pozitívnak kell lennie</span><span class="sxs-lookup"><span data-stu-id="3014c-110">The modulus by which residues are take, must be positive</span></span>



## <a name="output--bigint"></a><span data-ttu-id="3014c-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="3014c-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="3014c-112">Egész szám $r $0 és között, `modulus - 1` amely a `value - r` modulus alapján osztható</span><span class="sxs-lookup"><span data-stu-id="3014c-112">Integer $r$ between 0 and `modulus - 1` such that `value - r` is divisible by modulus</span></span>

## <a name="remarks"></a><span data-ttu-id="3014c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="3014c-113">Remarks</span></span>

<span data-ttu-id="3014c-114">Ez a függvény különbözik attól, hogy az operátor hogyan viselkedik a `%` C#-ban és a Q #-ban, ahogy az eredményben mindig nem negatív egész szám 0 és között `modulus - 1` , még akkor is, ha az érték negatív.</span><span class="sxs-lookup"><span data-stu-id="3014c-114">This function behaves different to how the operator `%` behaves in C# and Q# as in the result is always a non-negative integer between 0 and `modulus - 1`, even if value is negative.</span></span>