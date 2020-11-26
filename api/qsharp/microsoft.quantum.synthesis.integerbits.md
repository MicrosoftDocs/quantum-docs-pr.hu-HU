---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231092"
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