---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 0c5e29fbca8449f8122f2a9f988797e94e27da60
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717266"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="5ccf5-102">ApplyToFirstTwoQubitsCA művelet</span><span class="sxs-lookup"><span data-stu-id="5ccf5-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="5ccf5-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5ccf5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5ccf5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ccf5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5ccf5-105">Egy műveletet alkalmaz a regisztráció első két qubits.</span><span class="sxs-lookup"><span data-stu-id="5ccf5-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="5ccf5-106">A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="5ccf5-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5ccf5-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5ccf5-107">Input</span></span>

### <a name="op--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="5ccf5-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="5ccf5-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5ccf5-109">Az első két qubits alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="5ccf5-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5ccf5-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5ccf5-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5ccf5-111">Qubit a tömböt az első két qubits, amelynek a műveletét alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="5ccf5-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ccf5-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ccf5-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5ccf5-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5ccf5-113">Remarks</span></span>

<span data-ttu-id="5ccf5-114">Ez egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="5ccf5-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="5ccf5-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="5ccf5-115">See Also</span></span>

- [<span data-ttu-id="5ccf5-116">Microsoft. Quantum. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="5ccf5-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)