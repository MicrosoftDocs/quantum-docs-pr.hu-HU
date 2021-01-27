---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA
title: ApplyToFirstTwoQubitsA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 197f1da6682b100a0b71f3548727188c0ef6f7c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850681"
---
# <a name="applytofirsttwoqubitsa-operation"></a><span data-ttu-id="8d36f-102">ApplyToFirstTwoQubitsA művelet</span><span class="sxs-lookup"><span data-stu-id="8d36f-102">ApplyToFirstTwoQubitsA operation</span></span>

<span data-ttu-id="8d36f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d36f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d36f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d36f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d36f-105">Egy műveletet alkalmaz a regisztráció első két qubits.</span><span class="sxs-lookup"><span data-stu-id="8d36f-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="8d36f-106">A módosító `A` azt jelzi, hogy a művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="8d36f-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsA (op : ((Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="8d36f-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8d36f-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="8d36f-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d36f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="8d36f-109">Az első két qubits alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="8d36f-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="8d36f-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8d36f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8d36f-111">Qubit a tömböt az első két qubits, amelynek a műveletét alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="8d36f-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d36f-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d36f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d36f-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8d36f-113">Remarks</span></span>

<span data-ttu-id="8d36f-114">Ez egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="8d36f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="8d36f-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8d36f-115">See Also</span></span>

- [<span data-ttu-id="8d36f-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="8d36f-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)