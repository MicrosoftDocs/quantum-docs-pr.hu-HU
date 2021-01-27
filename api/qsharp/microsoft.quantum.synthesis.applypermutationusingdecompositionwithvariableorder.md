---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858870"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="f2f04-102">ApplyPermutationUsingDecompositionWithVariableOrder művelet</span><span class="sxs-lookup"><span data-stu-id="f2f04-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="f2f04-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f2f04-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f2f04-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2f04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2f04-105">A Permutes az amplitúdókat a dekompozíciós-alapú szintézis használatával, a kvantum-állapotban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="f2f04-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f2f04-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f2f04-106">Description</span></span>

<span data-ttu-id="f2f04-107">Ez a művelet az általános verziója, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" amelyben a változó sorrend megadható.</span><span class="sxs-lookup"><span data-stu-id="f2f04-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="f2f04-108">Egy másik változó megrendelése megváltoztatja a dekompozíciós sorozatot és az ellenőrzött kapuk esetében használt igazság-táblákat @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="f2f04-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="f2f04-109">Ezért a változó sorrend módosítása megváltoztatja a permutációk megvalósításához használt teljes kapuk számát.</span><span class="sxs-lookup"><span data-stu-id="f2f04-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="f2f04-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f2f04-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="f2f04-111">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f2f04-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f2f04-112">A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.</span><span class="sxs-lookup"><span data-stu-id="f2f04-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="f2f04-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f2f04-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f2f04-114">Egy $n $ elemből álló permutáció, amely 0-tól kezdődően kezdődik.</span><span class="sxs-lookup"><span data-stu-id="f2f04-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f2f04-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2f04-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2f04-116">$N $ qubits listája, amelyre a permutáció vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f2f04-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2f04-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2f04-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="f2f04-118">Példa</span><span class="sxs-lookup"><span data-stu-id="f2f04-118">Example</span></span>

<span data-ttu-id="f2f04-119">Művelet szintetizálása `SWAP` :</span><span class="sxs-lookup"><span data-stu-id="f2f04-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a><span data-ttu-id="f2f04-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f2f04-120">See Also</span></span>

- [<span data-ttu-id="f2f04-121">Microsoft. Quantum. szintézis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="f2f04-121">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="f2f04-122">Microsoft. Quantum. szintézis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="f2f04-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)