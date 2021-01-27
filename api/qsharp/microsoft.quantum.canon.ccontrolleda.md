---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 823d80182621691f4fa6f42246b3d671f3adfc3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840995"
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