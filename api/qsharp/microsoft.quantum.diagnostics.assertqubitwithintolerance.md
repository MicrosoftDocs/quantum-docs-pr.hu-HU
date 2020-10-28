---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712884"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="053fb-102">AssertQubitWithinTolerance művelet</span><span class="sxs-lookup"><span data-stu-id="053fb-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="053fb-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="053fb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="053fb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="053fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="053fb-105">Azt állítja, hogy a qubit a `q` Pauli Z operátor várt eigenstate található, egy adott toleranciával.</span><span class="sxs-lookup"><span data-stu-id="053fb-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="053fb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="053fb-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="053fb-107">várt: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="053fb-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="053fb-108">A qubit várható állapota a következő: `Zero` vagy `One` .</span><span class="sxs-lookup"><span data-stu-id="053fb-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="053fb-109">k: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="053fb-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="053fb-110">Az a qubit, amelynek az állapota érvényesítve van.</span><span class="sxs-lookup"><span data-stu-id="053fb-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="053fb-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="053fb-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="053fb-112">A várt eredményt visszaadó qubit mértékének valószínűségére vonatkozó tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="053fb-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="053fb-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="053fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="053fb-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="053fb-114">Remarks</span></span>

<span data-ttu-id="053fb-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> lehetővé teszi tetszőleges qubit-állapotok megadását, nem csak $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="053fb-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="053fb-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="053fb-116">See Also</span></span>

- [<span data-ttu-id="053fb-117">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="053fb-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)