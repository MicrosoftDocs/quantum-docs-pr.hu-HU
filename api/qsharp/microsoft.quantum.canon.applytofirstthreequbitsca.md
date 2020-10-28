---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717350"
---
# <a name="applytofirstthreequbitsca-operation"></a><span data-ttu-id="75085-102">ApplyToFirstThreeQubitsCA művelet</span><span class="sxs-lookup"><span data-stu-id="75085-102">ApplyToFirstThreeQubitsCA operation</span></span>

<span data-ttu-id="75085-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="75085-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="75085-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75085-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75085-105">Egy műveletet alkalmaz a regisztráció első három qubits.</span><span class="sxs-lookup"><span data-stu-id="75085-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="75085-106">A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="75085-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="75085-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="75085-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a><span data-ttu-id="75085-108">op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="75085-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="75085-109">Az első három qubits alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="75085-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="75085-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="75085-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="75085-111">Qubit a tömböt arra az első három qubits, amelynek a műveletét alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="75085-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75085-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75085-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="75085-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="75085-113">Remarks</span></span>

<span data-ttu-id="75085-114">Ez egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="75085-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="75085-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="75085-115">See Also</span></span>

- [<span data-ttu-id="75085-116">Microsoft. Quantum. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="75085-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)