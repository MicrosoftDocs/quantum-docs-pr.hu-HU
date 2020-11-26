---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 6d3ad9ca2e0d10c264f8020e1f34687f6cbc9f94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218189"
---
# <a name="applyquantumfouriertransform-operation"></a>ApplyQuantumFourierTransform művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a kis endian ábrázolásban.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="qs--littleendian"></a>QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A bemenet és a kimenet kis endian-kódolásban van feltételezve.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)