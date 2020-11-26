---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: 9024da4a457265c65a41ef681cfbb99ebd4989a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223357"
---
# <a name="computereciprocali-operation"></a>ComputeReciprocalI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Kiszámítja az 1/x értéket egy előjel nélküli egész x-re az egész szám osztással. Az eredmény az egész számként értelmezve lesz `floor(2^(2*n-1) / x)` .

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

n bites előjel nélküli egész szám


### <a name="result--littleendian"></a>eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

a 2n-bites kimenetnek kezdetben $ \ket $ értékűnek kell lennie {0} .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Az x = 0 bemenet esetén a kimenet minden esetben megjelenik.