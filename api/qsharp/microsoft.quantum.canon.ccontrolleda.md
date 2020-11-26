---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: cb72ca5b3dab99b9ee8a994ba9fde46e0eae5594
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207513"
---
# <a name="ccontrolleda-function"></a>CControlledA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz. Ha `false` nem történik semmi.
A módosító `A` azt jelzi, hogy a művelet adjointable.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)

Egy feltételesen alkalmazni kívánt művelet.



## <a name="output--boolt--unit--is-adj"></a>Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)

Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)