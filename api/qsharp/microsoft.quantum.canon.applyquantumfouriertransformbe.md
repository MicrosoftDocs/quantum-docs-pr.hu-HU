---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: ApplyQuantumFourierTransformBE művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841568"
---
# <a name="applyquantumfouriertransformbe-operation"></a>ApplyQuantumFourierTransformBE művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Végrehajtja a Quantum Fourier-transzformációt egy olyan kvantum-regiszteren, amely egy egész számot tartalmaz a big-endian ábrázolásban.

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="qs--bigendian"></a>QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

A kvantum-regiszter, amelyre a Quantum Fourier-transzformáció vonatkozik



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A bemenet és a kimenet nagy endian-kódolásban van feltételezve.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApproximateQFT](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)