---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 080414d208a2a0c114857db8e93efb4cd74a4d8d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222575"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="81e65-102">MultiplyByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="81e65-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="81e65-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81e65-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81e65-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81e65-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81e65-105">A qubit-regiszterben egy egész állandó használatával hajtja végre a moduláris szorzást.</span><span class="sxs-lookup"><span data-stu-id="81e65-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="81e65-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="81e65-106">Description</span></span>

<span data-ttu-id="81e65-107">`modulus`$N $ és $a $ jelöléssel jelezze nekünk `constMultiplier` .</span><span class="sxs-lookup"><span data-stu-id="81e65-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="81e65-108">Ezt követően a művelet egy egységes műveletet valósít meg, amelyet a következő Térkép határoz meg a számítási alapon: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ az összes $y $ és a $N-$1 $0 között.</span><span class="sxs-lookup"><span data-stu-id="81e65-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="81e65-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="81e65-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="81e65-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81e65-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81e65-111">Az állandó, amellyel a szorzót megszorozzuk.</span><span class="sxs-lookup"><span data-stu-id="81e65-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="81e65-112">A modulus értékének együtt kell lennie.</span><span class="sxs-lookup"><span data-stu-id="81e65-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="81e65-113">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81e65-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81e65-114">A szorzási művelet elvégzése többértékű `modulus` .</span><span class="sxs-lookup"><span data-stu-id="81e65-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="81e65-115">szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81e65-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81e65-116">A szám egy állandóval megszorozva.</span><span class="sxs-lookup"><span data-stu-id="81e65-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="81e65-117">Ez egy qubits-kódolású tömb, amely egy egész szám endian formátumú.</span><span class="sxs-lookup"><span data-stu-id="81e65-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81e65-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81e65-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="81e65-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="81e65-119">Remarks</span></span>

- <span data-ttu-id="81e65-120">Az áramköri diagramhoz és a magyarázathoz lásd a 7. ábrán a [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="81e65-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="81e65-121">Ez a művelet megfelel az U ₐ a [arXiv-ben: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="81e65-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>