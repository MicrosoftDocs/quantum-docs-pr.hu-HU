---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712282"
---
# <a name="knilldistill-operation"></a>KnillDistill művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Implementálja a Knill mágikus állapotának kimaradó algoritmusát.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Leírás

Az $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket \end{align}, $ $ értékű Magic State 15 hozzávetőleges példánya {8} {1} egy magasabb színvonalú másolatot eredményez.

## <a name="input"></a>Bevitel

### <a name="roughmagic--qubit"></a>roughMagic: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Egy olyan tizenöt qubits-bejegyzés, amely a mágikus állapot hozzávetőleges másolatait tartalmazza. A jelen desztilláló eljárás alkalmazása után `roughMagic[0]` egy jobb minőségű másolatot fog tartalmazni, és a regisztráció többi része visszaáll a $ \ket{00\cdots 0} $ állapotra.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Ha `true` az eljárás sikeres volt, és a jobb minőségű másolatot el kell fogadni. Ha `false` az eljárás sikertelen volt, és a regiszter állapotát nem definiált állapotúnak kell tekinteni.

## <a name="remarks"></a>Megjegyzések

Követjük a Knill algoritmusát.
A jelen implementáció azonban messze nem optimális, mivel túl sok qubits használ.
A rendszer befecskendezi a mágikus állapotokat ebben a rutinban, ebben az esetben jobb protokollok vannak.

## <a name="references"></a>Referencia

- [Knill](https://arxiv.org/abs/quant-ph/0402171)