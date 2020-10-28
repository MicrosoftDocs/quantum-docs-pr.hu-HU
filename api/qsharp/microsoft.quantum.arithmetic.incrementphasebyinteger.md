---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721073"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="4f9fe-102">IncrementPhaseByInteger művelet</span><span class="sxs-lookup"><span data-stu-id="4f9fe-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="4f9fe-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4f9fe-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4f9fe-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4f9fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4f9fe-105">Megnöveli egy előjel nélküli kvantum-regisztrációt egy klasszikus egész számmal, fázisok forgása alapján.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="4f9fe-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4f9fe-106">Description</span></span>

<span data-ttu-id="4f9fe-107">Tegyük fel, hogy az `target` előjel nélküli egész $x $ endian kódolásban kódolja, és a `increment` $a $ értékkel egyenlő.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="4f9fe-108">Ezt követően ez a művelet megvalósítja az egységes $ \ket{x} \mapsto \ket{x + a} $ értéket, ahol a Hozzáadás a maradékot a 2. számú ^ n $, ahol a $n = \texttt{Length (TARGET!)} $.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="4f9fe-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4f9fe-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="4f9fe-110">növekmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f9fe-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f9fe-111">Az az egész szám, amelynek a `target` értéke növekszik.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="4f9fe-112">cél: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f9fe-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="4f9fe-113">A kvantum-regisztrálás egy előjel nélküli egész számot használ a endian kódolással a kettős (QFT) alapon.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f9fe-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f9fe-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4f9fe-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4f9fe-115">Remarks</span></span>

<span data-ttu-id="4f9fe-116">Vegye figyelembe, hogy egyszerűsítettük az áramkört, mert a növekmény egy klasszikus állandó, nem pedig a kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="4f9fe-117">Tekintse meg a [ arXiv: Quant-pH/0008033v1 6. oldalának ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) ábráját az áramköri diagramhoz és magyarázathoz.</span><span class="sxs-lookup"><span data-stu-id="4f9fe-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="4f9fe-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="4f9fe-118">References</span></span>

- [<span data-ttu-id="4f9fe-119">*Thomas G. drapérier* , arXiv: Quant – pH/0008033</span><span class="sxs-lookup"><span data-stu-id="4f9fe-119"> *Thomas G. Draper* , arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="4f9fe-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4f9fe-120">See Also</span></span>

- [<span data-ttu-id="4f9fe-121">Microsoft. Quantum. aritmetika. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="4f9fe-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)