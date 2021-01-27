---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852394"
---
# <a name="noop-operation"></a>NoOp művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Végrehajtja az Identity műveletet (No-op) egy argumentumon.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

A művelet bármilyen típusú értéket igénybe vesz, és semmit sem tesz hozzá.
Ez akkor lehet hasznos, ha egy Művelettípus bemenete várható, de nem kell végrehajtania a műveletet.
Ha például egy adott hibajavítási szindróma azt jelzi, hogy a hiba nem történt meg, `NoOp<Qubit[]>` a megfelelő helyreállítási eljárás lehet.
Hasonlóképpen, ha egy művelet egy állapot-előkészítési eljárást vár bemenetként, `NoOp<Qubit[]>` felkészítheti a $ \ket{0 \cdots 0} $ állapotot.

## <a name="input"></a>Bevitel

### <a name="input--t"></a>bemenet: nem

A figyelmen kívül hagyott érték.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

Szinte minden esetben explicit módon meg kell adni a type paramétert `NoOp` . A például megegyezik a következővel: `NoOp<Qubit>` <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. belső. I](xref:Microsoft.Quantum.Intrinsic.I)