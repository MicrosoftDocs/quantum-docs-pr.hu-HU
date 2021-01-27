---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859214"
---
# <a name="applyunitary-operation"></a>ApplyUnitary művelet

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A 2 ^ n x 2 ^ n egységes mátrix által definiált kaput alkalmazza.

Sikertelen, ha a mátrix nem egységes, vagy nem megfelelő méretű.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="unitary--complex"></a>egységes: [komplex](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n x 2 ^ n egységes mátrix, amely leírja a műveletet.
Ha a mátrix nem egységes, vagy nem megfelelő méretű, kivételt vet fel.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubits, amelyre alkalmazni kell a műveletet – n hosszú regisztráció.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

