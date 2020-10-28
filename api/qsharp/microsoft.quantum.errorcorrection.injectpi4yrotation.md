---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712324"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Egyetlen qubit elforgatása a π/4 értékkel az Y tengelyen.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a>Leírás

Egy π/4 rotációs műveletet hajt végre `Y` .

Az elforgatás a mágikus állapot elfogyasztásával történik. Ez a másolat az állam $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .
\end{align} $ $

## <a name="input"></a>Bevitel

### <a name="data--qubit"></a>adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A $ \pi/$4 értékkel el$Y forgatható qubit.


### <a name="magic--qubit"></a>Magic: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egy qubit kezdetben a mágikus állapotban van. A művelet végrehajtása után `magic` a rendszer visszaadja a $ \ket {0} $ állapotot.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```qsharp
Ry(PI() / 4.0, data);
```

és

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Ez a művelet támogatja a (z `Adjoint` )-t, amely esetében ugyanaz a mágikus állapot használatos, de az adatqubit gyakorolt hatás a $-\ PI/4 $ $Y $-forgás.