---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: eb01b1b9fccc19f0e3f1fd5ee596b95d0d61563f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200543"
---
# <a name="recovercss-operation"></a>RecoverCSS művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott típus által leírt kvantum-kóddal hajtja végre a hibajavítások egy szakaszát `CSS` .

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Bevitel

### <a name="code--css"></a>kód: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

A Quantum CSS-hiba – a típusként csomagolt kód kijavítani `CSS` a kvantum-adatok kódolását és dekódolását, valamint a hiba-szindrómák mérésének módját.


### <a name="fnx--recoveryfn"></a>fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

A `RecoveryFn` amely az `Pauli[]` észlelt hibát javító műveletekkel leképezi az egyes $X $ Error szindrómát.


### <a name="fnz--recoveryfn"></a>fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

A `RecoveryFn` amely az `Pauli[]` észlelt hibát javító műveletekkel leképezi az egyes $Z $ Error szindrómát.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Olyan qubits tömbje, amelyben a stabilizátor kódja van meghatározva.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)