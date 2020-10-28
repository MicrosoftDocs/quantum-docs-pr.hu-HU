---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: ApplyXControlledOnTruthTable művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725250"
---
# <a name="applyxcontrolledontruthtable-operation"></a>ApplyXControlledOnTruthTable művelet

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag [](https://nuget.org/packages/)


A @"microsoft.quantum.intrinsic.x" művelet bekapcsolása `target` , ha a logikai függvény Igaz értéket ad meg `func` a klasszikus hozzárendeléshez a ben `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
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



## <a name="references"></a>Referencia

- [*N. LOUVER* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv: Quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken* , *Martin Roetteler* , arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szintézis. ApplyXControlledOnTruthTableWithCleanTarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)