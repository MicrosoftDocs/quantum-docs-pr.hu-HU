---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853458"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="fe0f2-102">AssertQubit művelet</span><span class="sxs-lookup"><span data-stu-id="fe0f2-102">AssertQubit operation</span></span>

<span data-ttu-id="fe0f2-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fe0f2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fe0f2-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fe0f2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fe0f2-105">Azt állítja be, hogy a qubit a `q` Pauli Z operátor várt eigenstate van.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="fe0f2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fe0f2-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="fe0f2-107">várt: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="fe0f2-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="fe0f2-108">A qubit várható állapota a következő: `Zero` vagy `One` .</span><span class="sxs-lookup"><span data-stu-id="fe0f2-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="fe0f2-109">k: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fe0f2-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fe0f2-110">Az a qubit, amelynek az állapota érvényesítve van.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe0f2-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe0f2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe0f2-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fe0f2-112">Remarks</span></span>

<span data-ttu-id="fe0f2-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> lehetővé teszi tetszőleges qubit-állapotok megadását, nem csak $Z $ eigenstates.</span><span class="sxs-lookup"><span data-stu-id="fe0f2-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe0f2-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fe0f2-114">See Also</span></span>

- [<span data-ttu-id="fe0f2-115">Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="fe0f2-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)