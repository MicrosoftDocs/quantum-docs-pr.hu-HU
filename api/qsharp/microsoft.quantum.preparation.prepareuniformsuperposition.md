---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854319"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A 0 és közötti kódolást biztosító állapotok egységes összeosztását hozza létre `nIndices - 1` .

Ez azt eredményezi, hogy ez az egységes $U $ a $0 $ és $M-$1 közötti összes számú államban egységes feladatot hoz létre, amely a \ket{0\cdots 0} $ értékű bemeneti állapottal rendelkezik. Más szóval, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

Az állapotok kívánt száma $M $ egységben.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A qubit-regisztráció, amely a számot tárolja a `LittleEndian` formátumban.
A regisztrációnak képesnek kell lennie a $M-$1 szám tárolására, és a rendszer azt feltételezi, hogy inicializálva van a $ \ket{0\cdots 0} $ állapotban.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

Az alábbi példa a $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ \ket{j} $ értéket állítja elő {5} $3 $ qubits.

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a>Megjegyzések

A művelet adjointable, de az ilyen esetekben a szükséges, hogy az első esetben egységes feltételt biztosítson `indexRegister` `nIndices` .