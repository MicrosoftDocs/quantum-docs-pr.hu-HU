---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711051"
---
# <a name="mresetz-operation"></a><span data-ttu-id="ab376-102">MResetZ művelet</span><span class="sxs-lookup"><span data-stu-id="ab376-102">MResetZ operation</span></span>

<span data-ttu-id="ab376-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ab376-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ab376-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab376-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab376-105">Egy qubit a Z alapján, és visszaállítja egy rögzített kezdeti állapotba a mérést követően.</span><span class="sxs-lookup"><span data-stu-id="ab376-105">Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="ab376-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ab376-106">Description</span></span>

<span data-ttu-id="ab376-107">Egy qubit mérést hajt végre a $Z $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.</span><span class="sxs-lookup"><span data-stu-id="ab376-107">Performs a single-qubit measurement in the $Z$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="ab376-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ab376-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="ab376-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ab376-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ab376-110">Egyetlen qubit kell mérni.</span><span class="sxs-lookup"><span data-stu-id="ab376-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ab376-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="ab376-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ab376-112">A `target` Pauli $Z $ alapján történő mérés eredménye.</span><span class="sxs-lookup"><span data-stu-id="ab376-112">The result of measuring `target` in the Pauli $Z$ basis.</span></span>