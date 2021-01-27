---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841005"
---
# <a name="ccontrolled-function"></a>CControlled függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz. Ha `false` nem történik semmi.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Bevitel

### <a name="op--t--unit"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy feltételesen alkalmazni kívánt művelet.



## <a name="output--boolt--unit"></a>Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A feltételesen alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. Quantum. Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. Quantum. Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)