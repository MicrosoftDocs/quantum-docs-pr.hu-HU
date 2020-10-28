---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717407"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="02b53-102">ApplyToFirstQubitC művelet</span><span class="sxs-lookup"><span data-stu-id="02b53-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="02b53-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02b53-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02b53-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02b53-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02b53-105">A művelet op-t alkalmazza a regisztráció első qubit.</span><span class="sxs-lookup"><span data-stu-id="02b53-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="02b53-106">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="02b53-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="02b53-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="02b53-107">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="02b53-108">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="02b53-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="02b53-109">Az első qubit alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="02b53-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="02b53-110">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="02b53-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="02b53-111">Qubit-tömb az első Qubit, amelynek a műveletét alkalmazza a rendszer</span><span class="sxs-lookup"><span data-stu-id="02b53-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="02b53-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02b53-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="02b53-113">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="02b53-113">See Also</span></span>

- [<span data-ttu-id="02b53-114">Microsoft. Quantum. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="02b53-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)