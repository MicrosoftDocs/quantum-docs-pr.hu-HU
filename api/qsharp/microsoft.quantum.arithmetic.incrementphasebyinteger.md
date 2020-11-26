---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222915"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="45f21-102">IncrementPhaseByInteger művelet</span><span class="sxs-lookup"><span data-stu-id="45f21-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="45f21-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="45f21-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="45f21-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45f21-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45f21-105">Megnöveli egy előjel nélküli kvantum-regisztrációt egy klasszikus egész számmal, fázisok forgása alapján.</span><span class="sxs-lookup"><span data-stu-id="45f21-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="45f21-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="45f21-106">Description</span></span>

<span data-ttu-id="45f21-107">Tegyük fel, hogy az `target` előjel nélküli egész $x $ endian kódolásban kódolja, és a `increment` $a $ értékkel egyenlő.</span><span class="sxs-lookup"><span data-stu-id="45f21-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="45f21-108">Ezt követően ez a művelet megvalósítja az egységes $ \ket{x} \mapsto \ket{x + a} $ értéket, ahol a Hozzáadás a maradékot a 2. számú ^ n $, ahol a $n = \texttt{Length (TARGET!)} $.</span><span class="sxs-lookup"><span data-stu-id="45f21-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="45f21-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="45f21-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="45f21-110">növekmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="45f21-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="45f21-111">Az az egész szám, amelynek a `target` értéke növekszik.</span><span class="sxs-lookup"><span data-stu-id="45f21-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="45f21-112">cél: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45f21-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="45f21-113">A kvantum-regisztrálás egy előjel nélküli egész számot használ a endian kódolással a kettős (QFT) alapon.</span><span class="sxs-lookup"><span data-stu-id="45f21-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45f21-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45f21-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="45f21-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="45f21-115">Remarks</span></span>

<span data-ttu-id="45f21-116">Vegye figyelembe, hogy egyszerűsítettük az áramkört, mert a növekmény egy klasszikus állandó, nem pedig a kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="45f21-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="45f21-117">Tekintse meg a [ arXiv: Quant-pH/0008033v1 6. oldalának ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) ábráját az áramköri diagramhoz és magyarázathoz.</span><span class="sxs-lookup"><span data-stu-id="45f21-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="45f21-118">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="45f21-118">References</span></span>

- [<span data-ttu-id="45f21-119">*Thomas G. drapérier*, arXiv: Quant – pH/0008033</span><span class="sxs-lookup"><span data-stu-id="45f21-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="45f21-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="45f21-120">See Also</span></span>

- [<span data-ttu-id="45f21-121">Microsoft. Quantum. aritmetika. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="45f21-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)