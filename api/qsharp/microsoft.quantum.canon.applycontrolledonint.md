---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845097"
---
# <a name="applycontrolledonint-operation"></a>ApplyControlledOnInt művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy egységes műveletet alkalmaz a cél-tételjegyzéken, ha a vezérlő regisztrálása állapot egy megadott pozitív egész számnak felel meg.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Nem negatív egész szám, amelyen a műveletet `oracle` ellenőrizni kell.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

Egy szabályozható, egységes művelet.


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Egy kvantum-regisztráció, amely a alkalmazást vezérli `oracle` .


### <a name="targetregister--t"></a>targetRegister: nem

Egy regisztráció, amelyre alkalmazni kell `oracle` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

A értéke `numberState` kis endian kódolással értelmezhető.

`numberState` legfeljebb 2 ^ \texttt{Length kell lennie (controlRegister)} – $1.
Például az `numberState = 537` azt jelenti, hogy az `oracle` csak akkor van alkalmazva, ha a és csak `controlRegister` a $ \ket $ állapotban van {537} .