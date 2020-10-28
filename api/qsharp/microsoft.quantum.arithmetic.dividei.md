---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721217"
---
# <a name="dividei-operation"></a>DivideI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Két kvantum egész számot oszt ki.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Leírás

`xs` a maradékot fogja tárolni `xs - floor(xs/ys) * ys` , és `result` megtartja `floor(xs/ys)` .

## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit osztalékot, a fennmaradó összeg helyébe lép.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

$n $ bites osztó


### <a name="result--littleendian"></a>eredmény: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit eredménynek kezdetben a $ \ket $ állapotban kell lennie, {0} és a rendszer az egész szám felosztásával váltja fel.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Standard eltolási és kivonási megközelítést használ a divízió megvalósításához.
Az ellenőrzött verzió speciális, így a kivonás nem igényel további vezérlőket.