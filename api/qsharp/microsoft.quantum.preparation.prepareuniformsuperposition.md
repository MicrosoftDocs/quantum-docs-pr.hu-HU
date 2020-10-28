---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709455"
---
# <a name="prepareuniformsuperposition-operation"></a>PrepareUniformSuperposition művelet

Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)

Csomag [](https://nuget.org/packages/)


A 0 és közötti kódolást biztosító állapotok egységes összeosztását hozza létre `nIndices - 1` .

Ez azt eredményezi, hogy ez az egységes $U $ a $0 $ és $M-$1 közötti összes számú államban egységes feladatot hoz létre, amely a \ket{0\cdots 0} $ értékű bemeneti állapottal rendelkezik. Más szóval, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.
\end{align} $ $.

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Bevitel

### <a name="nindices--int"></a>nIndices: [int](xref:microsoft.quantum.lang-ref.int)

Az állapotok kívánt száma $M $ egységben.


### <a name="indexregister--littleendian"></a>indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A qubit-regisztráció, amely a számot tárolja a `LittleEndian` formátumban.
A regisztrációnak képesnek kell lennie a $M-$1 szám tárolására, és a rendszer azt feltételezi, hogy inicializálva van a $ \ket{0\cdots 0} $ állapotban.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A művelet adjointable, de az ilyen esetekben a szükséges, hogy az első esetben egységes feltételt biztosítson `indexRegister` `nIndices` .