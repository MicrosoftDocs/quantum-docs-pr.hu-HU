---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724676"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="b1188-102">SetToBasisState művelet</span><span class="sxs-lookup"><span data-stu-id="b1188-102">SetToBasisState operation</span></span>

<span data-ttu-id="b1188-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="b1188-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="b1188-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1188-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1188-105">A qubit egy adott számítási állapotra állítja be a qubit mérésével, és szükség esetén egy kis tükrözés alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="b1188-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b1188-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b1188-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="b1188-107">kívánt: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="b1188-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="b1188-108">Az az állapot, amelynek alapján a qubit be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="b1188-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b1188-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b1188-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b1188-110">Az a qubit, amelynek az állapotát be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="b1188-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1188-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1188-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b1188-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b1188-112">Remarks</span></span>

<span data-ttu-id="b1188-113">Ennek a műveletnek a invariánsa a `M(q)` visszatérés után azonnal meghívja `SetToBasisState(result, q)` azt `result` .</span><span class="sxs-lookup"><span data-stu-id="b1188-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>