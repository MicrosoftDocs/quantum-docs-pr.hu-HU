---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721060"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="909b2-102">IncrementPhaseByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="909b2-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="909b2-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="909b2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="909b2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="909b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="909b2-105">Egy qubit-regiszter moduláris növekményét hajtja végre egy egész állandó értékkel.</span><span class="sxs-lookup"><span data-stu-id="909b2-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="909b2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="909b2-106">Description</span></span>

<span data-ttu-id="909b2-107">`increment`$A $, `modulus` $N $ és Integer szerint, $y $ kódolással jelezze nekünk `target` .</span><span class="sxs-lookup"><span data-stu-id="909b2-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="909b2-108">Ezután a művelet a következő átalakítást hajtja végre: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} egész számok kódolása kis endian formátumban történik QFT alapján.</span><span class="sxs-lookup"><span data-stu-id="909b2-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="909b2-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="909b2-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="909b2-110">növekmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="909b2-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="909b2-111">$A $ számú növekményt $y $ értékre kell felvenni.</span><span class="sxs-lookup"><span data-stu-id="909b2-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="909b2-112">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="909b2-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="909b2-113">Egész $N $, hogy a mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="909b2-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="909b2-114">cél: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="909b2-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="909b2-115">Egész $y $ a fázis-kódolású kis endian formátumban, amelyet `increment` a $a $ hozzáad a következőhöz:.</span><span class="sxs-lookup"><span data-stu-id="909b2-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="909b2-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="909b2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="909b2-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="909b2-117">Remarks</span></span>

<span data-ttu-id="909b2-118">Feltételezi, hogy `target` a legmagasabb bit 0 értékű.</span><span class="sxs-lookup"><span data-stu-id="909b2-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="909b2-119">Azt is feltételezi, hogy a célként megadott érték kisebb, mint $N $.</span><span class="sxs-lookup"><span data-stu-id="909b2-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="909b2-120">Az áramköri diagramhoz és a magyarázathoz lásd az 5. ábrát a következő [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="909b2-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="909b2-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="909b2-121">See Also</span></span>

- [<span data-ttu-id="909b2-122">Microsoft. Quantum. aritmetika. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="909b2-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)