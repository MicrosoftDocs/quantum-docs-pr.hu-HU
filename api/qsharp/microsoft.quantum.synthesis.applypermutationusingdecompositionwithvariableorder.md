---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725293"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="3f3e5-102">ApplyPermutationUsingDecompositionWithVariableOrder művelet</span><span class="sxs-lookup"><span data-stu-id="3f3e5-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="3f3e5-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3f3e5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f3e5-105">A Permutes az amplitúdókat a dekompozíciós-alapú szintézis használatával, a kvantum-állapotban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="3f3e5-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="3f3e5-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="3f3e5-106">Description</span></span>

<span data-ttu-id="3f3e5-107">Ez a művelet az általános verziója, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" amelyben a változó sorrend megadható.</span><span class="sxs-lookup"><span data-stu-id="3f3e5-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="3f3e5-108">Egy másik változó megrendelése megváltoztatja a dekompozíciós sorozatot és az ellenőrzött kapuk esetében használt igazság-táblákat @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="3f3e5-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="3f3e5-109">Ezért a változó sorrend módosítása megváltoztatja a permutációk megvalósításához használt teljes kapuk számát.</span><span class="sxs-lookup"><span data-stu-id="3f3e5-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="3f3e5-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3f3e5-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="3f3e5-111">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3f3e5-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3f3e5-112">A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.</span><span class="sxs-lookup"><span data-stu-id="3f3e5-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="3f3e5-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3f3e5-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3f3e5-114">Egy $n $ elemből álló permutáció, amely 0-tól kezdődően kezdődik.</span><span class="sxs-lookup"><span data-stu-id="3f3e5-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3f3e5-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3f3e5-116">$N $ qubits listája, amelyre a permutáció vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="3f3e5-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f3e5-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f3e5-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3f3e5-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3f3e5-118">See Also</span></span>

- [<span data-ttu-id="3f3e5-119">Microsoft. Quantum. szintézis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="3f3e5-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="3f3e5-120">Microsoft. Quantum. szintézis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="3f3e5-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)