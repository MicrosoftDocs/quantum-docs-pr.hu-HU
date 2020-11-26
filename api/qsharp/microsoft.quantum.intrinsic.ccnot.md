---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: 715796ddd915d80036933e3f1ceefa97aa62cecf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212477"
---
# <a name="ccnot-operation"></a><span data-ttu-id="074c1-102">CCNOT művelet</span><span class="sxs-lookup"><span data-stu-id="074c1-102">CCNOT operation</span></span>

<span data-ttu-id="074c1-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="074c1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="074c1-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="074c1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="074c1-105">A kettős vezérlésű – NOT (CCNOT) kaput alkalmazza három qubits.</span><span class="sxs-lookup"><span data-stu-id="074c1-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="074c1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="074c1-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="074c1-107">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="074c1-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="074c1-108">A CCNOT-kapu első vezérlőelem-qubit.</span><span class="sxs-lookup"><span data-stu-id="074c1-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="074c1-109">2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="074c1-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="074c1-110">A CCNOT Gate második vezérlőelem-qubit.</span><span class="sxs-lookup"><span data-stu-id="074c1-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="074c1-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="074c1-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="074c1-112">A CCNOT kapu cél qubit.</span><span class="sxs-lookup"><span data-stu-id="074c1-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="074c1-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="074c1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="074c1-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="074c1-114">Remarks</span></span>

<span data-ttu-id="074c1-115">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="074c1-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```