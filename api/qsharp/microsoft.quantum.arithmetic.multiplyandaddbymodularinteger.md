---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719812"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="06ee2-102">MultiplyAndAddByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="06ee2-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="06ee2-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="06ee2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="06ee2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06ee2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06ee2-105">Egy qubit-regiszterben egy moduláris szorzást és-hozzáadást végez az egész számok állandói alapján.</span><span class="sxs-lookup"><span data-stu-id="06ee2-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="06ee2-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="06ee2-106">Description</span></span>

<span data-ttu-id="06ee2-107">A $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ értéket implementálja egy adott modulus $N $, konstans szorzó $a $ és summand $y $ esetében.</span><span class="sxs-lookup"><span data-stu-id="06ee2-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="06ee2-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="06ee2-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="06ee2-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06ee2-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06ee2-110">Az egyes alapállapotok címkéjébe felvenni $a $ értéket.</span><span class="sxs-lookup"><span data-stu-id="06ee2-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="06ee2-111">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06ee2-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06ee2-112">Az a modulus $N $, amelyet a Hozzáadás és a szorzás is figyelembe vesz a tekintetében.</span><span class="sxs-lookup"><span data-stu-id="06ee2-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="06ee2-113">szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06ee2-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="06ee2-114">Egy olyan előjel nélküli egész szám, amelynek értékét fel kell venni az egyes alapállapotok címkéjébe `summand` .</span><span class="sxs-lookup"><span data-stu-id="06ee2-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="06ee2-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06ee2-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="06ee2-116">A művelet céljaként használandó, előjel nélküli egész számot jelölő kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="06ee2-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06ee2-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06ee2-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="06ee2-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="06ee2-118">Remarks</span></span>

- <span data-ttu-id="06ee2-119">Az áramköri diagramhoz és a magyarázathoz lásd a 6. ábrát a [arXiv 7. oldalán: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="06ee2-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="06ee2-120">Ez a művelet megfelel a CMULT (a) MOD (N) [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="06ee2-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="06ee2-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="06ee2-121">See Also</span></span>

- [<span data-ttu-id="06ee2-122">Microsoft. Quantum. aritmetika. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="06ee2-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)