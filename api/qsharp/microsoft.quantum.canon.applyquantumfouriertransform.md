---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: ApplyQuantumFourierTransform művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: fa8d135c0665f0a576229797d208b321ba0329a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717798"
---
# <a name="applyquantumfouriertransform-operation"></a>ApplyQuantumFourierTransform művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a kis endian ábrázolásban.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Bevitel

### <a name="qs--littleendian"></a>QS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A bemenet és a kimenet kis endian-kódolásban van feltételezve.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)