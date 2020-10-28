---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725264"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="e1a73-102">ApplyTransposition művelet</span><span class="sxs-lookup"><span data-stu-id="e1a73-102">ApplyTransposition operation</span></span>

<span data-ttu-id="e1a73-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e1a73-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e1a73-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1a73-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e1a73-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="e1a73-105">Description</span></span>

<span data-ttu-id="e1a73-106">Ez a művelet felcseréli az amplitúdót az indexben `a` az amplitúdónál az indexnél az `b` adott állapotú, `register` $n $ hosszúságú vektorban.</span><span class="sxs-lookup"><span data-stu-id="e1a73-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="e1a73-107">Ha `a` egyenlő `b` , az állapot-vektor nem módosul.</span><span class="sxs-lookup"><span data-stu-id="e1a73-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="e1a73-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e1a73-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e1a73-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1a73-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1a73-110">Első index (0 és $2 ^ n-$1 közötti értéknek kell lennie)</span><span class="sxs-lookup"><span data-stu-id="e1a73-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="e1a73-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1a73-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1a73-112">Második index (0 és $2 ^ n-$1 közötti értéknek kell lennie)</span><span class="sxs-lookup"><span data-stu-id="e1a73-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="e1a73-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e1a73-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e1a73-114">$N $ qubits listája, amelyre az átültetést alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="e1a73-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1a73-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1a73-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

