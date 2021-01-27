---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857399"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="b8673-102">ApplyPermutationUsingDecomposition művelet</span><span class="sxs-lookup"><span data-stu-id="b8673-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="b8673-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="b8673-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="b8673-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b8673-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b8673-105">A Permutes az amplitúdókat a dekompozíciós-alapú szintézis használatával, a kvantum-állapotban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="b8673-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b8673-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b8673-106">Description</span></span>

<span data-ttu-id="b8673-107">Ez az eljárás megvalósítja a dekompozíciós alapú szintézis megközelítését.</span><span class="sxs-lookup"><span data-stu-id="b8673-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="b8673-108">A bemenet egy \pi $ több mint $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, amely egy $n $-változó megfordítható logikai függvényt jelöl.</span><span class="sxs-lookup"><span data-stu-id="b8673-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="b8673-109">A iteratív algoritmus a következő lépéseket hajtja végre az egyes változók $i $-indexek esetében:</span><span class="sxs-lookup"><span data-stu-id="b8673-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="b8673-110">A számítási $ ((\ pi_l, \ pi_r), \pi ') $ úgy, hogy a $ \ pi_l $ és a $ \ pi_r $ lemezképek ne változtassák meg a BITS-elemeket a $i $ és a $ \pi ' $ értéknél nem változtatnak a bit $i $ értékkel az elemekben.</span><span class="sxs-lookup"><span data-stu-id="b8673-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="b8673-111">Állítsa be a $ \pi \leftarrow \pi ' $ értéket, és származtatja az igazság táblákat a $ \ pi_l $ és a $ \ pi_r $ érték alapján a nem rögzített elemek alapján.</span><span class="sxs-lookup"><span data-stu-id="b8673-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="b8673-112">Miután alkalmazza ezeket a lépéseket az összes változó indexre, a fennmaradó permutáció $ \pi $ lesz az identitás, és az összegyűjtött igazság táblák és indexek alapján az egyik @"microsoft.quantum.intrinsic.x" a művelettel az igazság-tábla által vezérelt műveletekkel is alkalmazható @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" .</span><span class="sxs-lookup"><span data-stu-id="b8673-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="b8673-113">A változó sorrend értéke $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="b8673-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="b8673-114">A műveletben megadhat egyéni változó sorrendet @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="b8673-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="b8673-115">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b8673-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="b8673-116">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b8673-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b8673-117">A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.</span><span class="sxs-lookup"><span data-stu-id="b8673-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="b8673-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b8673-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b8673-119">$N $ qubits listája, amelyre a permutáció vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="b8673-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b8673-120">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b8673-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="b8673-121">Példa</span><span class="sxs-lookup"><span data-stu-id="b8673-121">Example</span></span>

<span data-ttu-id="b8673-122">Művelet szintetizálása `SWAP` :</span><span class="sxs-lookup"><span data-stu-id="b8673-122">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="b8673-123">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="b8673-123">References</span></span>

- [<span data-ttu-id="b8673-124">*Alexis de Vos*, *Yvan van Rentergem*, ADV. in Math. of comm. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="b8673-124">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="b8673-125">*Mathias Soeken*, *Laura Tóthné*, *Gerhard W. Dueck*, *Rolf Drechsler*, szimbolikus számítások lapja 73 (2016), PP. 1--26</span><span class="sxs-lookup"><span data-stu-id="b8673-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="b8673-126">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b8673-126">See Also</span></span>

- [<span data-ttu-id="b8673-127">Microsoft. Quantum. szintézis. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="b8673-127">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="b8673-128">Microsoft. Quantum. szintézis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="b8673-128">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)