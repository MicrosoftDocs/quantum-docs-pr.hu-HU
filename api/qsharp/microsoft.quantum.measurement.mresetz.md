---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853744"
---
# <a name="mresetz-operation"></a><span data-ttu-id="3b378-102">MResetZ művelet</span><span class="sxs-lookup"><span data-stu-id="3b378-102">MResetZ operation</span></span>

<span data-ttu-id="3b378-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="3b378-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="3b378-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3b378-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b378-105">Egy qubit a Z alapján, és visszaállítja egy rögzített kezdeti állapotba a mérést követően.</span><span class="sxs-lookup"><span data-stu-id="3b378-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="3b378-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="3b378-106">Description</span></span>

<span data-ttu-id="3b378-107">Egy qubit mérést hajt végre a $Z $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.</span><span class="sxs-lookup"><span data-stu-id="3b378-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="3b378-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3b378-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="3b378-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b378-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b378-110">Egyetlen qubit kell mérni.</span><span class="sxs-lookup"><span data-stu-id="3b378-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3b378-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="3b378-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="3b378-112">A `target` Pauli $Z $ alapján történő mérés eredménye.</span><span class="sxs-lookup"><span data-stu-id="3b378-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>