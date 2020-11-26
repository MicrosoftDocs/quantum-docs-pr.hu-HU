---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 25ac2b35047b1c33a89149eae6d40f6f7ae3b454
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216914"
---
# <a name="ccontrolledc-function"></a>CControlledC függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz. Ha `false` nem történik semmi.
A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy feltételesen alkalmazni kívánt művelet.



## <a name="output--boolt--unit--is-ctl"></a>Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)