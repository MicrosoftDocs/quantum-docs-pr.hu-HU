---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222779"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Regisztrálja, hogy az előjel nélküli egész számot kódolja kis endian sorrendben. Az indextel rendelkező qubit `0` egy előjel nélküli egész szám legalacsonyabb részét kódolja.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Megjegyzések

`LittleEndian` `LE` A dokumentációnak megfelelően rövidítjük.