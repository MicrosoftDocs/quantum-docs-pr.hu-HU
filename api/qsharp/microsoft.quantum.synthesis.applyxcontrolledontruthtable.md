---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203297"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="20851-102">ApplyXControlledOnTruthTable művelet</span><span class="sxs-lookup"><span data-stu-id="20851-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="20851-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="20851-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="20851-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20851-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20851-105">A @"microsoft.quantum.intrinsic.x" művelet bekapcsolása `target` , ha a logikai függvény Igaz értéket ad meg `func` a klasszikus hozzárendeléshez a ben `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="20851-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="20851-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="20851-106">Description</span></span>

<span data-ttu-id="20851-107">A művelet végrehajtja az \begin{align} U\ket {x} \ ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, ahol a $x $ és a $y $ a `controlRegister` és a értéket képviseli `target` .</span><span class="sxs-lookup"><span data-stu-id="20851-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="20851-108">A (z) $f $ logikai függvény igaz táblaként jelöli meg egy nagy egész számot.</span><span class="sxs-lookup"><span data-stu-id="20851-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="20851-109">Például a bitstring a többségi függvényt jelképezi, `11101000` ahol a legjelentősebb bit `1` megfelel a bemeneti hozzárendelésnek `(1, 1, 1)` , és a legkevésbé jelentős bit `0` megfelel a bemeneti hozzárendelésnek `(0, 0, 0)` .</span><span class="sxs-lookup"><span data-stu-id="20851-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="20851-110">A nagy egész számot `0xE8L` hexadecimális jelöléssel vagy `232L` decimális jelöléssel lehet megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="20851-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="20851-111">Az `L` utótag azt jelzi, hogy az állandó típusa típusú `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="20851-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="20851-112">A jelen képviseletről további részleteket a The [Truth Tables kataban](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)találhat.</span><span class="sxs-lookup"><span data-stu-id="20851-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="20851-113">A megvalósítás a és a Gates használatát teszi lehetővé @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="20851-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="20851-114">Bevitel</span><span class="sxs-lookup"><span data-stu-id="20851-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="20851-115">függvény: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="20851-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="20851-116">Nagy egész számként jelölt logikai igazság tábla</span><span class="sxs-lookup"><span data-stu-id="20851-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="20851-117">controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="20851-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="20851-118">A vezérlő qubits regisztrálása</span><span class="sxs-lookup"><span data-stu-id="20851-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="20851-119">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="20851-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="20851-120">Cél qubit</span><span class="sxs-lookup"><span data-stu-id="20851-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="20851-121">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20851-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="20851-122">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="20851-122">References</span></span>

- [<span data-ttu-id="20851-123">*N. LOUVER*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="20851-123">*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="20851-124">*Mathias Soeken*, *Martin Roetteler*, arXiv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="20851-124">*Mathias Soeken*, *Martin Roetteler*, arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="20851-125">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="20851-125">See Also</span></span>

- [<span data-ttu-id="20851-126">Microsoft. Quantum. szintézis. ApplyXControlledOnTruthTableWithCleanTarget</span><span class="sxs-lookup"><span data-stu-id="20851-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)