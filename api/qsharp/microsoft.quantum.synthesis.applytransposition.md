---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203314"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="9f146-102">ApplyTransposition művelet</span><span class="sxs-lookup"><span data-stu-id="9f146-102">ApplyTransposition operation</span></span>

<span data-ttu-id="9f146-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9f146-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9f146-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f146-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9f146-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="9f146-105">Description</span></span>

<span data-ttu-id="9f146-106">Ez a művelet felcseréli az amplitúdót az indexben `a` az amplitúdónál az indexnél az `b` adott állapotú, `register` $n $ hosszúságú vektorban.</span><span class="sxs-lookup"><span data-stu-id="9f146-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="9f146-107">Ha `a` egyenlő `b` , az állapot-vektor nem módosul.</span><span class="sxs-lookup"><span data-stu-id="9f146-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="9f146-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9f146-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="9f146-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f146-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f146-110">Első index (0 és $2 ^ n-$1 közötti értéknek kell lennie)</span><span class="sxs-lookup"><span data-stu-id="9f146-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="9f146-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f146-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f146-112">Második index (0 és $2 ^ n-$1 közötti értéknek kell lennie)</span><span class="sxs-lookup"><span data-stu-id="9f146-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9f146-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9f146-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9f146-114">$N $ qubits listája, amelyre az átültetést alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="9f146-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9f146-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9f146-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

