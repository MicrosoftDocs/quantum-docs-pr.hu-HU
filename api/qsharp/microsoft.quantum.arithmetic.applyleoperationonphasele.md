---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: ApplyLEOperationOnPhaseLE művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: ff8e9424b1fc179f25ca926520338a4bbbcd04c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721636"
---
# <a name="applyleoperationonphasele-operation"></a>ApplyLEOperationOnPhaseLE művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Egy olyan műveletet alkalmaz, amely egy <xref:microsoft.quantum.arithmetic.phaselittleendian> típusú cél-regiszterben bemenetként regisztrálja a regisztrációt <xref:microsoft.quantum.arithmetic.littleendian> .

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>Bevitel

### <a name="op--littleendian--unit"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az alkalmazni kívánt művelet.


### <a name="target--phaselittleendian"></a>cél: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

A regisztráció, amelyre a művelet vonatkozik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A rendszer átalakítja a regisztrációt a `LittleEndian` használatával, <xref:microsoft.quantum.canon.qftle> és ezután visszaküldi az eredeti képviseletét az alkalmazása után `op` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLEC](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [Microsoft. Quantum. Canon. ApplyLEOperationonPhaseLECA](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)