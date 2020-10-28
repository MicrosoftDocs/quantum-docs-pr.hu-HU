---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719848"
---
# <a name="integerbits-function"></a>IntegerBits függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag [](https://nuget.org/packages/)


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