---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840683"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott művelethez tartozó Trotter – Suzuki integrátort megvalósító műveletet ad vissza.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

A felbontani kívánt műveletek száma az idő lépésekben.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy művelet, amely elfogad egy index bemenetet (típus `Int` ) és egy időbemenetet (típus `Double` ) a dekompozícióhoz.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Kiválasztja a használni kívánt Trotter-Suzuki-integrátor sorrendjét.
1. megrendelés és a 2., 4., 6. rendelés,... jelenleg támogatottak.



## <a name="output--doublet--unit--is-adj--ctl"></a>Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL

A Trotter – Suzuki integrátor egységes megvalósítását adja vissza, ahol az első paraméter az `Double` integrációs lépés mérete, a második paraméter pedig a cél.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a típus, amely az egyes időpontokban cselekszik; általában a `Qubit[]` vagy a `Qubit` .

## <a name="remarks"></a>Megjegyzések

Ha `order` egyenlő értékűre van meghívva `1` , ez a függvény egy olyan műveletet ad vissza, amelyet a legalacsonyabb rendű Trotter – Suzuki integrátor $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, ahol követte a [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) jelölését, és hagyja, hogy a $ \lambda $ legyen az evolúciós idő (amelyet a visszaadott művelet első bemenete képvisel), és engedje, hogy \{ a $ H_j \} _ {j = 1} ^ {m} $ legyen a (ferde Hermitian) dinamikus generátorok olyan készlete, amely integrálva van, így `op(j, lambda, _)` az egységes operátor szimulálja $e ^ {H_j \lambda} $.

Hasonlóképpen, a `order` `2` -ból a második sorrend szimmetrikus Trotter – Suzuki integrátor $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

A `order` [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)rekurzív felépítése révén a rendszer még nagyobb értékeket is megvalósít.

## <a name="references"></a>Hivatkozások

- [*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)