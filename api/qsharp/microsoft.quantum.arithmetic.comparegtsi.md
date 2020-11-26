---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223493"
---
# <a name="comparegtsi-operation"></a>CompareGTSI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


A burkoló az aláírt egész szám összehasonlításához: `result = xs > ys` .

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="xs--signedlittleendian"></a>xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

Első $n $ bites szám


### <a name="ys--signedlittleendian"></a>[SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian) :

Második $n $ bites szám


### <a name="result--qubit"></a>eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Akkor lesz felfordítva, ha $xs >



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

