---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223476"
---
# <a name="comparegti-operation"></a>CompareGTI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Burkoló az egész szám összehasonlításához: `result = x > y` .

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Első $n $ bites szám


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

Második $n $ bites szám


### <a name="result--qubit"></a>eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Akkor lesz felfordítva, ha $x > y $



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

