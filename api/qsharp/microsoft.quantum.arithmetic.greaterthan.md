---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846636"
---
# <a name="greaterthan-operation"></a>GreaterThan művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Több mint összehasonlítást alkalmaz a qubit-regiszterbe kódolt két egész szám között, az összehasonlítás eredményétől függően a célként megadott qubit.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Szigorúan nagyobb, mint két egész szám összehasonlítása $x $ és $y $, a qubit-ben kódolva, az XS és az időpontot. Ha $x > y $, akkor az eredmény qubit lesz tükrözve, ellenkező esetben az eredmény qubit meg fogja őrizni az állapotát.

## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A LittleEndian qubit regisztrálja az első egész számot $x $ értékkel.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

A LittleEndian qubit regisztrálja a második egész számot $y $ értékkel.


### <a name="result--qubit"></a>eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Egyetlen qubit, amely akkor lesz felfordítva, ha $x > y $ értéket.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A (z) $x-y = (x ' + y) ' $ értéket használja, ahol a "az egymást kiegészítő értéket jelöli.

## <a name="references"></a>Hivatkozások

- Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener, Martin Roetteler, Garai Viktória M. Svore: "faktoring by 2n + 2 qubits a Toffoli-alapú moduláris szorzás", 2016 https://arxiv.org/abs/1611.07995