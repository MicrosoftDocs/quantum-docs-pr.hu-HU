---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717393"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="c3fda-102">ApplyToFirstQubitCA művelet</span><span class="sxs-lookup"><span data-stu-id="c3fda-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="c3fda-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3fda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3fda-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c3fda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c3fda-105">A művelet op-t alkalmazza a regisztráció első qubit.</span><span class="sxs-lookup"><span data-stu-id="c3fda-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="c3fda-106">A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="c3fda-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c3fda-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c3fda-107">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="c3fda-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c3fda-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c3fda-109">Az első qubit alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="c3fda-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c3fda-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c3fda-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c3fda-111">Qubit-tömb az első Qubit, amelynek a műveletét alkalmazza a rendszer</span><span class="sxs-lookup"><span data-stu-id="c3fda-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3fda-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3fda-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c3fda-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c3fda-113">See Also</span></span>

- [<span data-ttu-id="c3fda-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="c3fda-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)