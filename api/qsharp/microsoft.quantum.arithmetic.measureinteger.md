---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720965"
---
# <a name="measureinteger-operation"></a>MeasureInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


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