---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721216"
---
# <a name="copymostsignificantbit-operation"></a>CopyMostSignificantBit művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Egy olyan qubit-regiszter legjelentősebb részét másolja, amely `from` előjel nélküli egész számot jelképez a qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="from--littleendian"></a>Forrás: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Az előjel nélküli egész szám, amelyből a legmagasabb bit át lett másolva.
az egész szám kódolása kis endian formátumban történik.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a qubit, amelyben a legmagasabb bit másolása zajlik. A bit kódolás számítási alapon történik.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. aritmetika. LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)