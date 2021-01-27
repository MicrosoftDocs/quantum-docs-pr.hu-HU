---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846569"
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