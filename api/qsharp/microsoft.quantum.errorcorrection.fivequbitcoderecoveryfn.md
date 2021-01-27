---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853129"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt a függvényt adja vissza, amely leképezi a hiba-szindrómát a megfelelő hiba kijavítani a Pauli-operátorok számára az 5, 1, 3 ⟧ kvantum-kód ⟦.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Kimenet: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Olyan típusú függvény, `RecoveryFn` amely egy tünetegyüttes-mérést végez `Result[]` , és az `Pauli[]` észlelt hibát javító operátorokat adja vissza.

## <a name="remarks"></a>Megjegyzések

Az $1 $ súlyozású összes hiba megismétlésével összesen $3 \ alkalommal 5 = 15 $ lehetséges, nem triviális tünetegyüttest kapunk.
Az identitással együtt a rendszer felépíti a hibát tartalmazó táblázatot és a megfelelő szindrómát. Az 5 qubit-kód esetében ezt a táblázatot a következő adja meg: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ $Y _i $ beszerzésével, a $X _i $ és a $Z $ szindrómák hozzáadásával. Vegye figyelembe, hogy a tábla keresésének helyreállítását úgy adja meg, hogy a bitvectors egész számmá (kis endian használatával) konvertálja.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)