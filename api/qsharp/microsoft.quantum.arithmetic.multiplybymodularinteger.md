---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719789"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="ea082-102">MultiplyByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="ea082-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="ea082-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ea082-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ea082-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea082-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea082-105">A qubit-regiszterben egy egész állandó használatával hajtja végre a moduláris szorzást.</span><span class="sxs-lookup"><span data-stu-id="ea082-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="ea082-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ea082-106">Description</span></span>

<span data-ttu-id="ea082-107">`modulus`$N $ és $a $ jelöléssel jelezze nekünk `constMultiplier` .</span><span class="sxs-lookup"><span data-stu-id="ea082-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="ea082-108">Ezt követően a művelet egy egységes műveletet valósít meg, amelyet a következő Térkép határoz meg a számítási alapon: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ az összes $y $ és a $N-$1 $0 között.</span><span class="sxs-lookup"><span data-stu-id="ea082-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="ea082-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ea082-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="ea082-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea082-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea082-111">Az állandó, amellyel a szorzót megszorozzuk.</span><span class="sxs-lookup"><span data-stu-id="ea082-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="ea082-112">A modulus értékének együtt kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ea082-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="ea082-113">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ea082-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ea082-114">A szorzási művelet elvégzése többértékű `modulus` .</span><span class="sxs-lookup"><span data-stu-id="ea082-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="ea082-115">szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ea082-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ea082-116">A szám egy állandóval megszorozva.</span><span class="sxs-lookup"><span data-stu-id="ea082-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="ea082-117">Ez egy qubits-kódolású tömb, amely egy egész szám endian formátumú.</span><span class="sxs-lookup"><span data-stu-id="ea082-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea082-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea082-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ea082-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ea082-119">Remarks</span></span>

- <span data-ttu-id="ea082-120">Az áramköri diagramhoz és a magyarázathoz lásd a 7. ábrán a [arXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="ea082-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="ea082-121">Ez a művelet megfelel az U ₐ a [arXiv-ben: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="ea082-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>