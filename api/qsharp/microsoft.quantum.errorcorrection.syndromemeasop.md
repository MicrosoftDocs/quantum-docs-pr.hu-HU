---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850055"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="55b6d-102">SyndromeMeasOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="55b6d-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="55b6d-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="55b6d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="55b6d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55b6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55b6d-105">Egy olyan műveletet jelöl, amely egy hiba-javító kód blokkolásának mérésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="55b6d-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="55b6d-106">Példa</span><span class="sxs-lookup"><span data-stu-id="55b6d-106">Example</span></span>

<span data-ttu-id="55b6d-107">Mérték szindrómák a bit-flip Code $S = \langle ZZI, IZZ \rangle $ a semmiből qubits használata nem hibatűrő módon:</span><span class="sxs-lookup"><span data-stu-id="55b6d-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="55b6d-108">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="55b6d-108">Remarks</span></span>

<span data-ttu-id="55b6d-109">Az aláírás `(LogicalRegister => Syndrome)` egy olyan műveletet jelöl, amely közösen működik a qubits `LogicalRegister` és néhány kiegészítő qubits, majd a kiegészítő qubits mérésével, amely a `Syndrome` mérések értékeit jelképezi `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="55b6d-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="55b6d-110">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="55b6d-110">See Also</span></span>

- [<span data-ttu-id="55b6d-111">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="55b6d-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="55b6d-112">Microsoft. Quantum. ErrorCorrection. szindróma</span><span class="sxs-lookup"><span data-stu-id="55b6d-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)