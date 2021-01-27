---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848349"
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



## <a name="example"></a>Példa

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Megjegyzések

Ez a függvény kiszámítja a valós modulusot úgy, hogy a valós sort becsomagolja az egység körére, majd megkeresi a bemenetnek megfelelő egység kör szögét.
A `minValue` bemenet ezután hatékonyan megadja az egység kör kivágásának helyét.