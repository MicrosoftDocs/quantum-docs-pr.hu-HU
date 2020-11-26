---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: a5ca9b366f7ff477070e21fea047ff04b425439c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203433"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="0f483-102">ApplyPermutationUsingDecompositionWithVariableOrder művelet</span><span class="sxs-lookup"><span data-stu-id="0f483-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="0f483-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0f483-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0f483-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f483-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0f483-105">A Permutes az amplitúdókat a dekompozíciós-alapú szintézis használatával, a kvantum-állapotban kell megadni.</span><span class="sxs-lookup"><span data-stu-id="0f483-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0f483-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="0f483-106">Description</span></span>

<span data-ttu-id="0f483-107">Ez a művelet az általános verziója, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" amelyben a változó sorrend megadható.</span><span class="sxs-lookup"><span data-stu-id="0f483-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="0f483-108">Egy másik változó megrendelése megváltoztatja a dekompozíciós sorozatot és az ellenőrzött kapuk esetében használt igazság-táblákat @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="0f483-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="0f483-109">Ezért a változó sorrend módosítása megváltoztatja a permutációk megvalósításához használt teljes kapuk számát.</span><span class="sxs-lookup"><span data-stu-id="0f483-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="0f483-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0f483-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="0f483-111">dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0f483-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0f483-112">A 0-tól kezdődően 2 ^ n $ elemből álló permutáció.</span><span class="sxs-lookup"><span data-stu-id="0f483-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="0f483-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0f483-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0f483-114">Egy $n $ elemből álló permutáció, amely 0-tól kezdődően kezdődik.</span><span class="sxs-lookup"><span data-stu-id="0f483-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="0f483-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0f483-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0f483-116">$N $ qubits listája, amelyre a permutáció vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="0f483-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f483-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f483-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0f483-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0f483-118">See Also</span></span>

- [<span data-ttu-id="0f483-119">Microsoft. Quantum. szintézis. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="0f483-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="0f483-120">Microsoft. Quantum. szintézis. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="0f483-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)