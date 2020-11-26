---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223289"
---
# <a name="copymostsignificantbit-operation"></a>CopyMostSignificantBit művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan qubit-regiszter legjelentősebb részét másolja, amely `from` előjel nélküli egész számot jelképez a qubit `target` .

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
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