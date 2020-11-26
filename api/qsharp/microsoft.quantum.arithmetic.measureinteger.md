---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: e3ff06e5cbb2ef8a63e4ad12308b382347c90fc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222643"
---
# <a name="measureinteger-operation"></a>MeasureInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A kvantum-regiszter tartalmát méri, és egy egész számra konvertálja. A mérés a standard számítási alapon történik, azaz a eigenbasis `PauliZ` .

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a>Bevitel

### <a name="target--littleendian"></a>cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A kis endian kódolású kvantum-regisztráció.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Előjel nélküli egész szám, amely a mért értéket tartalmazza `target` .

## <a name="remarks"></a>Megjegyzések

Ez a művelet visszaállítja a bemeneti regisztrációját a $ \ket{00\cdots 0} $ állapotra, amely alkalmas a célszámítógép visszaengedésére.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. MeasureIntegerBE](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)