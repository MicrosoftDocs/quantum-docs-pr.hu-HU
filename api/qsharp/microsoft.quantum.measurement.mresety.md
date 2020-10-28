---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725012"
---
# <a name="mresety-operation"></a><span data-ttu-id="43ecf-102">MResetY művelet</span><span class="sxs-lookup"><span data-stu-id="43ecf-102">MResetY operation</span></span>

<span data-ttu-id="43ecf-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="43ecf-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="43ecf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="43ecf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="43ecf-105">Egyetlen qubit mér az Y-ben, és visszaállítja a mérést követő rögzített kezdeti állapotba.</span><span class="sxs-lookup"><span data-stu-id="43ecf-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="43ecf-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="43ecf-106">Description</span></span>

<span data-ttu-id="43ecf-107">Egy qubit mérést hajt végre a $Y $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.</span><span class="sxs-lookup"><span data-stu-id="43ecf-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="43ecf-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="43ecf-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="43ecf-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="43ecf-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="43ecf-110">Egyetlen qubit kell mérni.</span><span class="sxs-lookup"><span data-stu-id="43ecf-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="43ecf-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="43ecf-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="43ecf-112">A `target` Pauli $Y $ alapján történő mérés eredménye.</span><span class="sxs-lookup"><span data-stu-id="43ecf-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>