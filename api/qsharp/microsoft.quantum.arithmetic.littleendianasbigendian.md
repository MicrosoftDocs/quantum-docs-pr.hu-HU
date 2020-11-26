---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 3cdcd18f06bf43d109c9f5e69f319f9d33b96bfc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222745"
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