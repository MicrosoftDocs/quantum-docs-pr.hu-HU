---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843369"
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