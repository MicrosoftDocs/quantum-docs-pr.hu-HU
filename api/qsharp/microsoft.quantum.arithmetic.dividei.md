---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223306"
---
# <a name="dividei-operation"></a>DivideI művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Két kvantum egész számot oszt ki.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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