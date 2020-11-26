---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 494f11c8129175ddd84c6539f5e9df1a758e8a82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194134"
---
# <a name="mresetz-operation"></a><span data-ttu-id="e93e6-102">MResetZ művelet</span><span class="sxs-lookup"><span data-stu-id="e93e6-102">MResetZ operation</span></span>

<span data-ttu-id="e93e6-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e93e6-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e93e6-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e93e6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e93e6-105">Egy qubit a Z alapján, és visszaállítja egy rögzített kezdeti állapotba a mérést követően.</span><span class="sxs-lookup"><span data-stu-id="e93e6-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="e93e6-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e93e6-106">Description</span></span>

<span data-ttu-id="e93e6-107">Egy qubit mérést hajt végre a $Z $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.</span><span class="sxs-lookup"><span data-stu-id="e93e6-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="e93e6-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e93e6-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="e93e6-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e93e6-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e93e6-110">Egyetlen qubit kell mérni.</span><span class="sxs-lookup"><span data-stu-id="e93e6-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e93e6-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="e93e6-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e93e6-112">A `target` Pauli $Z $ alapján történő mérés eredménye.</span><span class="sxs-lookup"><span data-stu-id="e93e6-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>