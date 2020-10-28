---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717406"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="11ee3-102">ApplyToFirstQubitA művelet</span><span class="sxs-lookup"><span data-stu-id="11ee3-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="11ee3-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="11ee3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="11ee3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11ee3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11ee3-105">Egy műveletet alkalmaz a regisztráció első qubit.</span><span class="sxs-lookup"><span data-stu-id="11ee3-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="11ee3-106">A módosító `A` azt jelzi, hogy a művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="11ee3-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="11ee3-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="11ee3-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="11ee3-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="11ee3-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="11ee3-109">Az első qubit alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="11ee3-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="11ee3-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="11ee3-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="11ee3-111">Qubit-tömb az első Qubit, amelynek a műveletét alkalmazza a rendszer</span><span class="sxs-lookup"><span data-stu-id="11ee3-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="11ee3-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11ee3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="11ee3-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="11ee3-113">See Also</span></span>

- [<span data-ttu-id="11ee3-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="11ee3-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)