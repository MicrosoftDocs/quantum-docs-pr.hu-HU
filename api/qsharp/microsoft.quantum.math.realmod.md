---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228253"
---
# <a name="realmod-function"></a>RealMod függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Két valós szám közötti modulus kiszámítása.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Bevitel

### <a name="value--double"></a>érték: [Double](xref:microsoft.quantum.lang-ref.double)

Egy valós szám $x $, amely a modulusát veszi figyelembe.


### <a name="modulo--double"></a>[egyoldalas: dupla](xref:microsoft.quantum.lang-ref.double)

Egy valós szám, amely a $x $ modulusát veszi figyelembe a tekintetében.


### <a name="minvalue--double"></a>minValue: [dupla](xref:microsoft.quantum.lang-ref.double)

A függvény által visszaadott legkisebb érték.



## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Megjegyzések

Ez a függvény kiszámítja a valós modulusot úgy, hogy a valós sort becsomagolja az egység körére, majd megkeresi a bemenetnek megfelelő egység kör szögét.
A `minValue` bemenet ezután hatékonyan megadja az egység kör kivágásának helyét.