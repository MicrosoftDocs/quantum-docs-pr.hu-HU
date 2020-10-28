---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: ApplyControlledOnBitString művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718360"
---
# <a name="applycontrolledonbitstring-operation"></a>ApplyControlledOnBitString művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy egységes műveletet alkalmaz a cél-tételjegyzéken, amelyet egy adott bit-maszk által meghatározott állapotban kell vezérelni.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Bevitel

### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Az adott egységes műveletnek a-on való vezérlésére szolgáló kis sztring.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

A cél-regisztráción alkalmazandó egységes művelet.


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Egy kvantum-regisztráció, amely a alkalmazást vezérli `oracle` .


### <a name="targetregister--t"></a>targetRegister: nem

A célként megadott regiszter, amelyet bemenetként kell átadni `oracle` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

A által megadott minta `bits` rövidebb lehet, mint `controlRegister` , amelynél a rendszer figyelmen kívül hagyja a további vezérlési qubits (azaz nem a $ \ket {0} $, sem a $ \ket $ értéket sem {1} ).
Ha `bits` a értéke hosszabb `controlRegister` , hiba történik.

Például az `bits = [0,1,0,0,1]` azt jelenti, hogy az `oracle` csak akkor van alkalmazva, ha a, és csak akkor, ha `controlRegister` a \ket {0} \ket {1} \ket {0} \ket {0} \ket {1} $ állapotban van.