---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: 1cf2bd944b4dcaadeeca96fa0f576250590962e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827602"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Függvény helyreállítási Pauli-műveletekhez az adott szindrómára vonatkozóan a ⟦ 3, 1, 1 ⟧ bit flip Code értékre való táblázatos kereséssel.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Olyan típusú függvény, `RecoveryFn` amely egy tünetegyüttes-mérést végez, `Result[]` és az `Pauli[]` észlelt hibát javító műveleteket adja vissza.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)