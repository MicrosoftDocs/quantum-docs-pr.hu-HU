---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 7395996e75c5a1c0c5d13f76d9ec76acae5683c7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200407"
---
# <a name="steanecoderecoveryfns-function"></a>SteaneCodeRecoveryFns függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A kombinált X-és Z-⟦ a (Z) 7, 1, 3 ⟧ Steane kvantum-kód stabilizátor-csoportjának egy részét.

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a>Kimenet: ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))

A szindrómát használó típusú függvények rekordja, amely `RecoveryFn` `Result[]` az `Pauli[]` észlelt hibát javító műveleteket adja vissza.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryZ](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)