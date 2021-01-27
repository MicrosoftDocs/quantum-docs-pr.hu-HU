---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841338"
---
# <a name="applytohead-operation"></a>ApplyToHead művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy műveletet alkalmaz egy tömb első elemére.

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Leírás

A művelet `op` és a célok tömbje `targets` érvényes `op(Head(targets))` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy alkalmazni kívánt művelet.


### <a name="targets--t"></a>célok: 'T []

A célok tömbje, amelyből az első lesz alkalmazva `op` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az alkalmazni kívánt művelet bemeneti típusa.

## <a name="example"></a>Példa

A következő Q # kódrészletek egyenértékűek:

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. Quantum. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Quantum. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)