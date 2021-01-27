---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855582"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="a398e-102">ApplyTransposition művelet</span><span class="sxs-lookup"><span data-stu-id="a398e-102">ApplyTransposition operation</span></span>

<span data-ttu-id="a398e-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a398e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a398e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a398e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a398e-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="a398e-105">Description</span></span>

<span data-ttu-id="a398e-106">Ez a művelet felcseréli az amplitúdót az indexben `a` az amplitúdónál az indexnél az `b` adott állapotú, `register` $n $ hosszúságú vektorban.</span><span class="sxs-lookup"><span data-stu-id="a398e-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="a398e-107">Ha `a` egyenlő `b` , az állapot-vektor nem módosul.</span><span class="sxs-lookup"><span data-stu-id="a398e-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="a398e-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a398e-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="a398e-109">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a398e-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a398e-110">Első index (0 és $2 ^ n-$1 közötti értéknek kell lennie)</span><span class="sxs-lookup"><span data-stu-id="a398e-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="a398e-111">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a398e-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a398e-112">Második index (0 és $2 ^ n-$1 közötti értéknek kell lennie)</span><span class="sxs-lookup"><span data-stu-id="a398e-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="a398e-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a398e-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a398e-114">$N $ qubits listája, amelyre az átültetést alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a398e-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a398e-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a398e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="a398e-116">Példa</span><span class="sxs-lookup"><span data-stu-id="a398e-116">Example</span></span>

<span data-ttu-id="a398e-117">A Number állapotok egységes felhelyezésének előkészítése $ | 1 \ rangle $, $ | 2 \ rangle $ és $ | 3 \ rangle $ on 2 qubits.</span><span class="sxs-lookup"><span data-stu-id="a398e-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```