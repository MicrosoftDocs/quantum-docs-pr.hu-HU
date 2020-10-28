---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721109"
---
# <a name="incrementbyinteger-operation"></a><span data-ttu-id="6b436-102">IncrementByInteger művelet</span><span class="sxs-lookup"><span data-stu-id="6b436-102">IncrementByInteger operation</span></span>

<span data-ttu-id="6b436-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6b436-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6b436-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b436-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b436-105">Megnöveli egy előjel nélküli kvantum-regisztrációt egy klasszikus egész számmal, fázisok forgása alapján.</span><span class="sxs-lookup"><span data-stu-id="6b436-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="6b436-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6b436-106">Description</span></span>

<span data-ttu-id="6b436-107">Tegyük fel, hogy az `target` előjel nélküli egész $x $ endian kódolásban kódolja, és a `increment` $a $ értékkel egyenlő.</span><span class="sxs-lookup"><span data-stu-id="6b436-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="6b436-108">Ezt követően ez a művelet megvalósítja az egységes $ \ket{x} \mapsto \ket{x + a} $ értéket, ahol a Hozzáadás a maradékot a 2. számú ^ n $, ahol a $n = \texttt{Length (TARGET!)} $.</span><span class="sxs-lookup"><span data-stu-id="6b436-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6b436-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6b436-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="6b436-110">növekmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6b436-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6b436-111">Az az egész szám, amelynek a `target` értéke növekszik.</span><span class="sxs-lookup"><span data-stu-id="6b436-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="6b436-112">cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6b436-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6b436-113">A kvantum-regisztráció előjel nélküli egész számot használ kis endian kódolással.</span><span class="sxs-lookup"><span data-stu-id="6b436-113">A quantum register encoding an unsigned integer using little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b436-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b436-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

