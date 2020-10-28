---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Művelet helyreállítása
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: a659399f51794a4edc1d2ff43da84e46797103fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712212"
---
# <a name="recover-operation"></a>Művelet helyreállítása

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Egy adott típus által leírt kvantum-kóddal hajtja végre a hibajavítások egy szakaszát `QECC` .

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Bevitel

### <a name="code--qecc"></a>kód: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Kvantum-hiba – a típusként csomagolt kód kijavítani `QECC` a kvantum-adatok kódolását és dekódolását, valamint a hiba-szindrómák mérésének módját.


### <a name="fn--recoveryfn"></a>FN: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

A az `RecoveryFn` `Pauli[]` észlelt hibát javító műveletekkel leképezi az egyes hibákat.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Olyan qubits tömbje, amelyben a stabilizátor kódja van meghatározva.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [Microsoft. Quantum. ErrorCorrection. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)