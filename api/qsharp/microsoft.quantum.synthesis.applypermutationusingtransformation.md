---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: a05b433eae2612bbf5c87522c4ef251976184aa8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192060"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="16a1e-102">ApplyPermutationUsingTransformation művelet</span><span class="sxs-lookup"><span data-stu-id="16a1e-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="16a1e-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="16a1e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="16a1e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16a1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16a1e-105">A Permutes az átalakítási alapú szintézis használatával egy olyan kvantum-állapotot adott meg, amely egy permutációt használ.</span><span class="sxs-lookup"><span data-stu-id="16a1e-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="16a1e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="16a1e-106">Description</span></span>

<span data-ttu-id="16a1e-107">Ez az eljárás megvalósítja az egyirányú átalakításon alapuló szintézis megközelítését.</span><span class="sxs-lookup"><span data-stu-id="16a1e-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="16a1e-108">A bemenet egy \pi $ több mint $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, amely egy $n $-változó visszafordítható logikai függvényt jelöl.</span><span class="sxs-lookup"><span data-stu-id="16a1e-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="16a1e-109">Az algoritmus a következő lépésekkel hajtja végre a iteratív:</span><span class="sxs-lookup"><span data-stu-id="16a1e-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="16a1e-110">Keresse meg a legkisebb $x $ értéket, amely $x \ne \pi (x) = y $.</span><span class="sxs-lookup"><span data-stu-id="16a1e-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="16a1e-111">Több vezérelt Toffoli-művelet, amelyek a kimenetekre vonatkoznak, a $ \pi (x) = x $ értéket, és nem változtatja meg a $ \pi (x) $ értéket az összes $x "< x $</span><span class="sxs-lookup"><span data-stu-id="16a1e-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="16a1e-112">Bevitel</span><span class="sxs-lookup"><span data-stu-id="16a1e-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="16a1e-113">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="16a1e-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="16a1e-114">A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.</span><span class="sxs-lookup"><span data-stu-id="16a1e-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="16a1e-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="16a1e-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="16a1e-116">$N $ qubits listája, amelyre a permutáció vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="16a1e-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16a1e-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16a1e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="16a1e-118">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="16a1e-118">References</span></span>

- [<span data-ttu-id="16a1e-119">*D. Michael Miller*, *Dmitrij Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, PP. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="16a1e-119">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="16a1e-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, PP. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="16a1e-120">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="16a1e-121">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="16a1e-121">See Also</span></span>

- [<span data-ttu-id="16a1e-122">Microsoft. Quantum. szintézis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="16a1e-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)