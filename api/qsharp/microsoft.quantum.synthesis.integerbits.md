---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855401"
---
# <a name="integerbits-function"></a>IntegerBits függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az összes olyan pozíciót adja vissza, amelyben egy egész számú bit be van állítva.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

Nem negatív szám.


### <a name="length--int"></a>Hossz: [int](xref:microsoft.quantum.lang-ref.int)

A bináris kiterjesztésű bitek száma `value` .



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Az összes bitet tartalmazó tömb (0-tól kezdődően), amely a bináris kiterjesztésben 1 az `value` összes bit pozícióig `length - 1` .  A tömbben az összes pozíciót növekvő sorrendben rendezi a rendszer.

## <a name="example"></a>Példa

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```