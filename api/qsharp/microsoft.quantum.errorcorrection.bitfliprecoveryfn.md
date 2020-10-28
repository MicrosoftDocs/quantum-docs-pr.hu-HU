---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712493"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Függvény helyreállítási Pauli-műveletekhez az adott szindrómára vonatkozóan a ⟦ 3, 1, 1 ⟧ bit flip Code értékre való táblázatos kereséssel.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Olyan típusú függvény, `RecoveryFn` amely egy tünetegyüttes-mérést végez, `Result[]` és az `Pauli[]` észlelt hibát javító műveleteket adja vissza.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)