---
uid: Microsoft.Quantum.Math.ModL
title: ModL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723108"
---
# <a name="modl-function"></a>ModL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Egy szám modulusát adja vissza egy másik számra vonatkozóan.

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a>Bevitel

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A bemeneti $a $, amelynek a modulusát vissza kell adni.


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az a szám, amelynek a $a $ értékét vissza kell adni.



## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A modulus $a \bmod b $.