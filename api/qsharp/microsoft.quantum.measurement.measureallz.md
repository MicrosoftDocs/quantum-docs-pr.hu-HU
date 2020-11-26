---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227080"
---
# <a name="measureallz-operation"></a><span data-ttu-id="ddd63-102">MeasureAllZ művelet</span><span class="sxs-lookup"><span data-stu-id="ddd63-102">MeasureAllZ operation</span></span>

<span data-ttu-id="ddd63-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ddd63-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ddd63-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddd63-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddd63-105">Közösen méri a qubits-regisztrációt a Pauli Z alapján.</span><span class="sxs-lookup"><span data-stu-id="ddd63-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="ddd63-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ddd63-106">Description</span></span>

<span data-ttu-id="ddd63-107">A qubits regiszterét méri a $Z \otimes Z \otimes \cdots \otimes Z $ alapján, amely a teljes regiszter paritását jelképezi.</span><span class="sxs-lookup"><span data-stu-id="ddd63-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="ddd63-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ddd63-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="ddd63-109">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ddd63-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ddd63-110">A mérendő regisztráció.</span><span class="sxs-lookup"><span data-stu-id="ddd63-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ddd63-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="ddd63-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ddd63-112">A \otimes \cdots \otimes Z $ \otimes $Z mérésének eredménye.</span><span class="sxs-lookup"><span data-stu-id="ddd63-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>