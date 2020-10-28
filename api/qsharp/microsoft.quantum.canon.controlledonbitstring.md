---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716441"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy olyan egységes műveletet ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott bit-maszknak felel meg.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Leírás

Ennek a függvénynek a kimenete egy olyan művelet, amely egy egységes átalakítással $U $, amely \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{BITS} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align}, ahol a $V $ egy egységes átalakítás, amely a művelet műveletét jelöli `oracle` .

## <a name="input"></a>Bevitel

### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Az adott egységes műveletnek a-on való vezérlésére szolgáló kis sztring.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

A cél-regisztráción alkalmazandó egységes művelet.



## <a name="output--qubitt--unit-adj--ctl"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], nem) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL

Egy egységes művelet, amely `oracle` a cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a bit maszknak `bits` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

A által megadott minta `bits` rövidebb lehet, mint `controlRegister` , amelynél a rendszer figyelmen kívül hagyja a további vezérlési qubits (azaz nem a $ \ket {0} $, sem a $ \ket $ értéket sem {1} ).
Ha `bits` a értéke hosszabb `controlRegister` , hiba történik.

Egy logikai tömb `bits` és egy egységes művelet miatt `oracle` a függvény kimenete egy olyan művelet, amely a következő lépéseket hajtja végre:

* alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely megfelel a `false` ; elemének `bits` ;
* `Controlled oracle`a vezérlő és a cél regiszterekre vonatkozik;
* alkalmazzon egy `X` műveletet a vezérlési regiszter minden olyan qubit, amely az `false` újra elemnek felel meg `bits` , hogy visszaadja a vezérlő regisztrálását az eredeti állapotába.

A leálltak kimenete `Controlled` olyan speciális eset, `ControlledOnBitString` ahol `bits` egyenlő `[true, ..., true]` .