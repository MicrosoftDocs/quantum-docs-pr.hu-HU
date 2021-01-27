---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855563"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable művelet

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A @"microsoft.quantum.intrinsic.x" művelet bekapcsolása `target` , ha a logikai függvény Igaz értéket ad meg `func` a klasszikus hozzárendeléshez a ben `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

A művelet végrehajtja az \begin{align} U\ket {x} \ ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, ahol a $x $ és a $y $ a `controlRegister` és a értéket képviseli `target` .

A (z) $f $ logikai függvény igaz táblaként jelöli meg egy nagy egész számot.
Például a bitstring a többségi függvényt jelképezi, `11101000` ahol a legjelentősebb bit `1` megfelel a bemeneti hozzárendelésnek `(1, 1, 1)` , és a legkevésbé jelentős bit `0` megfelel a bemeneti hozzárendelésnek `(0, 0, 0)` .
A nagy egész számot `0xE8L` hexadecimális jelöléssel vagy `232L` decimális jelöléssel lehet megjeleníteni.  Az `L` utótag azt jelzi, hogy az állandó típusa típusú `BigInt` .
A jelen képviseletről további részleteket a The [Truth Tables kataban](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)találhat.

A megvalósítás a és a Gates használatát teszi lehetővé @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .

## <a name="input"></a>Bevitel

### <a name="func--bigint"></a>függvény: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Nagy egész számként jelölt logikai igazság tábla


### <a name="controlregister--qubit"></a>controlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A vezérlő qubits regisztrálása


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Cél qubit



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Hivatkozások

- [*N. LOUVER*, *J. Siewert*, PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken*, *Martin Roetteler*, arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szintézis. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)