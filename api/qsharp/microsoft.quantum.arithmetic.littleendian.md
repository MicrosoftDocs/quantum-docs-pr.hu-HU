---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721048"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Regisztrálja, hogy az előjel nélküli egész számot kódolja kis endian sorrendben. Az indextel rendelkező qubit `0` egy előjel nélküli egész szám legalacsonyabb részét kódolja.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Megjegyzések

`LittleEndian` `LE` A dokumentációnak megfelelően rövidítjük.