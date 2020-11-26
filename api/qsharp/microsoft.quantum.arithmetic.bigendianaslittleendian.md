---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 5f5d7dc6e08a13fbdc45f9d11c93c29cfcf90bf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223629"
---
# <a name="bigendianaslittleendian-function"></a>BigEndianAsLittleEndian függvény

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy `BigEndian` qubit-regisztrációt alakít át egy `LittleEndian` qubit-regiszterbe a qubit sorrend megfordításával.

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a>Bevitel

### <a name="input--bigendian"></a>bemenet: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

A Qubit-regisztráció `BigEndian` formátuma.



## <a name="output--littleendian"></a>Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A Qubit-regisztráció `LittleEndian` formátuma.