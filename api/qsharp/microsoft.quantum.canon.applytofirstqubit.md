---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 381f8d689fba1984ba7fa287d658578bd5b6c48c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850733"
---
# <a name="applytofirstqubit-operation"></a><span data-ttu-id="34210-102">ApplyToFirstQubit művelet</span><span class="sxs-lookup"><span data-stu-id="34210-102">ApplyToFirstQubit operation</span></span>

<span data-ttu-id="34210-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="34210-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="34210-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34210-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34210-105">Egy műveletet alkalmaz a regisztráció első qubit.</span><span class="sxs-lookup"><span data-stu-id="34210-105">Applies an operation to the first qubit in the register.</span></span>

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="34210-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="34210-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="34210-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34210-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="34210-108">Az első qubit alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="34210-108">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="34210-109">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="34210-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="34210-110">Qubit-tömb az első Qubit, amelynek a műveletét alkalmazza a rendszer</span><span class="sxs-lookup"><span data-stu-id="34210-110">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="34210-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="34210-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="34210-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="34210-112">See Also</span></span>

- [<span data-ttu-id="34210-113">Microsoft. Quantum. Canon. ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="34210-113">Microsoft.Quantum.Canon.ApplyToFirstQubitA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [<span data-ttu-id="34210-114">Microsoft. Quantum. Canon. ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="34210-114">Microsoft.Quantum.Canon.ApplyToFirstQubitC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [<span data-ttu-id="34210-115">Microsoft. Quantum. Canon. ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="34210-115">Microsoft.Quantum.Canon.ApplyToFirstQubitCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)