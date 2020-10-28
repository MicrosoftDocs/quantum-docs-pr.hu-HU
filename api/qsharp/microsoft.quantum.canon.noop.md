---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715755"
---
# <a name="noop-operation"></a>NoOp művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Végrehajtja az Identity műveletet (No-op) egy argumentumon.

```qsharp
operation NoOp<'T> (input : 'T) : Unit
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