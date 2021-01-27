---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843078"
---
# <a name="littleendianasbigendian-function"></a>LittleEndianAsBigEndian függvény

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy `LittleEndian` qubit-regisztrációt alakít át egy `BigEndian` qubit-regiszterbe a qubit sorrend megfordításával.

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a>Bevitel

### <a name="input--littleendian"></a>bemenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A Qubit-regisztráció `LittleEndian` formátuma.



## <a name="output--bigendian"></a>Kimenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

A Qubit-regisztráció `BigEndian` formátuma.