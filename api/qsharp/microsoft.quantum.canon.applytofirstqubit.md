---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 99439229e2c3d5a10073669cf1e742f6de3d7618
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717421"
---
# <a name="applytofirstqubit-operation"></a><span data-ttu-id="d5cbc-102">ApplyToFirstQubit művelet</span><span class="sxs-lookup"><span data-stu-id="d5cbc-102">ApplyToFirstQubit operation</span></span>

<span data-ttu-id="d5cbc-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5cbc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5cbc-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5cbc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5cbc-105">Egy műveletet alkalmaz a regisztráció első qubit.</span><span class="sxs-lookup"><span data-stu-id="d5cbc-105">Applies an operation to the first qubit in the register.</span></span>

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="d5cbc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d5cbc-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="d5cbc-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5cbc-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d5cbc-108">Az első qubit alkalmazandó művelet</span><span class="sxs-lookup"><span data-stu-id="d5cbc-108">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="d5cbc-109">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d5cbc-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d5cbc-110">Qubit-tömb az első Qubit, amelynek a műveletét alkalmazza a rendszer</span><span class="sxs-lookup"><span data-stu-id="d5cbc-110">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5cbc-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5cbc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d5cbc-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d5cbc-112">See Also</span></span>

- [<span data-ttu-id="d5cbc-113">Microsoft. Quantum. Canon. ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="d5cbc-113">Microsoft.Quantum.Canon.ApplyToFirstQubitA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [<span data-ttu-id="d5cbc-114">Microsoft. Quantum. Canon. ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="d5cbc-114">Microsoft.Quantum.Canon.ApplyToFirstQubitC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [<span data-ttu-id="d5cbc-115">Microsoft. Quantum. Canon. ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="d5cbc-115">Microsoft.Quantum.Canon.ApplyToFirstQubitCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)