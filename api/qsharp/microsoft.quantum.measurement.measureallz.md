---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711078"
---
# <a name="measureallz-operation"></a><span data-ttu-id="6c171-102">MeasureAllZ művelet</span><span class="sxs-lookup"><span data-stu-id="6c171-102">MeasureAllZ operation</span></span>

<span data-ttu-id="6c171-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="6c171-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="6c171-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c171-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c171-105">Közösen méri a qubits-regisztrációt a Pauli Z alapján.</span><span class="sxs-lookup"><span data-stu-id="6c171-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="6c171-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6c171-106">Description</span></span>

<span data-ttu-id="6c171-107">A qubits regiszterét méri a $Z \otimes Z \otimes \cdots \otimes Z $ alapján, amely a teljes regiszter paritását jelképezi.</span><span class="sxs-lookup"><span data-stu-id="6c171-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="6c171-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6c171-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="6c171-109">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6c171-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6c171-110">A mérendő regisztráció.</span><span class="sxs-lookup"><span data-stu-id="6c171-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="6c171-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="6c171-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="6c171-112">A \otimes \cdots \otimes Z $ \otimes $Z mérésének eredménye.</span><span class="sxs-lookup"><span data-stu-id="6c171-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>