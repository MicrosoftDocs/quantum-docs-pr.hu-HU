---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854638"
---
# <a name="mresety-operation"></a><span data-ttu-id="1e879-102">MResetY művelet</span><span class="sxs-lookup"><span data-stu-id="1e879-102">MResetY operation</span></span>

<span data-ttu-id="1e879-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="1e879-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="1e879-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1e879-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1e879-105">Egyetlen qubit mér az Y-ben, és visszaállítja a mérést követő rögzített kezdeti állapotba.</span><span class="sxs-lookup"><span data-stu-id="1e879-105">Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.</span></span>

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a><span data-ttu-id="1e879-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="1e879-106">Description</span></span>

<span data-ttu-id="1e879-107">Egy qubit mérést hajt végre a $Y $-alapon, és biztosítja, hogy a rendszer visszaadja a qubit a \ket $ értékre {0} a mérés után.</span><span class="sxs-lookup"><span data-stu-id="1e879-107">Performs a single-qubit measurement in the $Y$-basis, and ensures that the qubit is returned to $\ket{0}$ following the measurement.</span></span>

## <a name="input"></a><span data-ttu-id="1e879-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1e879-108">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="1e879-109">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1e879-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1e879-110">Egyetlen qubit kell mérni.</span><span class="sxs-lookup"><span data-stu-id="1e879-110">A single qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="1e879-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="1e879-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="1e879-112">A `target` Pauli $Y $ alapján történő mérés eredménye.</span><span class="sxs-lookup"><span data-stu-id="1e879-112">The result of measuring `target` in the Pauli $Y$ basis.</span></span>