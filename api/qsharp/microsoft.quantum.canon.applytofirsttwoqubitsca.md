---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 5bea9ec1be1fc379823877684c81e99f86807d89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850665"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="60a9f-102">ApplyToFirstTwoQubitsCA művelet</span><span class="sxs-lookup"><span data-stu-id="60a9f-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="60a9f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60a9f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60a9f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60a9f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60a9f-105">Egy műveletet alkalmaz a regisztráció első két qubits.</span><span class="sxs-lookup"><span data-stu-id="60a9f-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="60a9f-106">A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="60a9f-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="60a9f-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="60a9f-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="60a9f-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="60a9f-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="60a9f-109">Az első két qubits alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="60a9f-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="60a9f-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="60a9f-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="60a9f-111">Qubit a tömböt az első két qubits, amelynek a műveletét alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="60a9f-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60a9f-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60a9f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="60a9f-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="60a9f-113">Remarks</span></span>

<span data-ttu-id="60a9f-114">Ez egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="60a9f-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="60a9f-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="60a9f-115">See Also</span></span>

- [<span data-ttu-id="60a9f-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="60a9f-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)