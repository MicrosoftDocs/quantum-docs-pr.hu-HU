---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200254"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="bd963-102">SyndromeMeasOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="bd963-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="bd963-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="bd963-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="bd963-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd963-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd963-105">Egy olyan műveletet jelöl, amely egy hiba-javító kód blokkolásának mérésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="bd963-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="bd963-106">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bd963-106">Remarks</span></span>

<span data-ttu-id="bd963-107">Az aláírás `(LogicalRegister => Syndrome)` egy olyan műveletet jelöl, amely közösen működik a qubits `LogicalRegister` és néhány kiegészítő qubits, majd a kiegészítő qubits mérésével, amely a `Syndrome` mérések értékeit jelképezi `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="bd963-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd963-108">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="bd963-108">See Also</span></span>

- [<span data-ttu-id="bd963-109">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="bd963-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="bd963-110">Microsoft. Quantum. ErrorCorrection. szindróma</span><span class="sxs-lookup"><span data-stu-id="bd963-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)