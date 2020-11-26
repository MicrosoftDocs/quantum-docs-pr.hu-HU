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
# <a name="syndromemeasop-user-defined-type"></a>SyndromeMeasOp-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan műveletet jelöl, amely egy hiba-javító kód blokkolásának mérésére szolgál.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Megjegyzések

Az aláírás `(LogicalRegister => Syndrome)` egy olyan műveletet jelöl, amely közösen működik a qubits `LogicalRegister` és néhány kiegészítő qubits, majd a kiegészítő qubits mérésével, amely a `Syndrome` mérések értékeit jelképezi `Result[]` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. szindróma](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)