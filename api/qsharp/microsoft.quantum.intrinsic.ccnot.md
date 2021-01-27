---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819029"
---
# <a name="ccnot-operation"></a><span data-ttu-id="899c3-102">CCNOT művelet</span><span class="sxs-lookup"><span data-stu-id="899c3-102">CCNOT operation</span></span>

<span data-ttu-id="899c3-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="899c3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="899c3-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="899c3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="899c3-105">A kettős vezérlésű – NOT (CCNOT) kaput alkalmazza három qubits.</span><span class="sxs-lookup"><span data-stu-id="899c3-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="899c3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="899c3-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="899c3-107">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="899c3-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="899c3-108">A CCNOT-kapu első vezérlőelem-qubit.</span><span class="sxs-lookup"><span data-stu-id="899c3-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="899c3-109">2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="899c3-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="899c3-110">A CCNOT Gate második vezérlőelem-qubit.</span><span class="sxs-lookup"><span data-stu-id="899c3-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="899c3-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="899c3-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="899c3-112">A CCNOT kapu cél qubit.</span><span class="sxs-lookup"><span data-stu-id="899c3-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="899c3-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="899c3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="899c3-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="899c3-114">Remarks</span></span>

<span data-ttu-id="899c3-115">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="899c3-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```