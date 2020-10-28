---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713039"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="f8fc7-102">AssertAllZeroWithinTolerance művelet</span><span class="sxs-lookup"><span data-stu-id="f8fc7-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="f8fc7-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f8fc7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f8fc7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8fc7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8fc7-105">Azt állítja, hogy a megadott qubits mind a $ \ket {0} $ állapotba kerülnek egy adott toleranciával.</span><span class="sxs-lookup"><span data-stu-id="f8fc7-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="f8fc7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f8fc7-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="f8fc7-107">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f8fc7-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f8fc7-108">A qubits $ \ket $ állapotban kell lennie {0} .</span><span class="sxs-lookup"><span data-stu-id="f8fc7-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="f8fc7-109">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f8fc7-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f8fc7-110">Pontosság, amellyel az állapotnak $ \ket $ állapotban kell lennie {0}</span><span class="sxs-lookup"><span data-stu-id="f8fc7-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8fc7-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8fc7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="f8fc7-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f8fc7-112">See Also</span></span>

- [<span data-ttu-id="f8fc7-113">Microsoft. Quantum. Diagnostics. AssertQubitWithinTolerance</span><span class="sxs-lookup"><span data-stu-id="f8fc7-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)