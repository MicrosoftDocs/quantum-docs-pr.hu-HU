---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720401"
---
# <a name="realmod-function"></a>RealMod függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


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