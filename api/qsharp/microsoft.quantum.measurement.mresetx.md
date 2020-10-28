---
uid: Microsoft.Quantum.Measurement.MResetX
title: MResetX művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetX
qsharp.summary: Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: a16d7405388b560edcdb6c36b6668791f7ba1398
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724999"
---
# <a name="mresetx-operation"></a><span data-ttu-id="ae135-102">MResetX művelet</span><span class="sxs-lookup"><span data-stu-id="ae135-102">MResetX operation</span></span>

<span data-ttu-id="ae135-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ae135-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ae135-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae135-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae135-105">Egy qubit X alapon, és a mérték után visszaállítja egy rögzített kezdeti állapotba.</span><span class="sxs-lookup"><span data-stu-id="ae135-105">Measures a single qubit in the X basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetX (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="ae135-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ae135-106">Description</span></span>

<span data-ttu-id="ae135-107">Egy qubit mérést hajt végre a $X $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.</span><span class="sxs-lookup"><span data-stu-id="ae135-107">Performs a single-qubit measurement in the $X$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="ae135-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ae135-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="ae135-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ae135-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ae135-110">Egyetlen qubit kell mérni.</span><span class="sxs-lookup"><span data-stu-id="ae135-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ae135-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="ae135-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ae135-112">A `target` Pauli $X $ alapján történő mérés eredménye.</span><span class="sxs-lookup"><span data-stu-id="ae135-112">The result of measuring `target` in the Pauli $X$ basis.</span></span>