---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721360"
---
# <a name="bigendian-user-defined-type"></a>BigEndian-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Regisztrálja, hogy a rendszer egy előjel nélküli egész számot kódol a big-endian sorrendben. Az indextel rendelkező qubit `0` a legmagasabb, előjel nélküli egész számot kódolja.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Megjegyzések

`BigEndian` `BE` A dokumentációnak megfelelően rövidítjük.