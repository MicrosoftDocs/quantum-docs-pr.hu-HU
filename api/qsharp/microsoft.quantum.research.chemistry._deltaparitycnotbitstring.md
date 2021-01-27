---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 3dd2d299a094577d377780d731e76287815e8d03
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847603"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring függvény

Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)

Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


A klasszikus feldolgozási lépése `ApplyDeltaParity` .
Ez kiszámítja a vezérlési qubits listáját, amely kiértékeli a paritásos különbözetet két PQRS között... a páros hossz feltételei.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Bevitel

### <a name="prevfermionicterm--int"></a>prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Megjegyzések

Ez azt feltételezi, hogy a feltételek hossza páros.
Kiszámítja a két kifejezés közötti paritásos különbözeti vezérlők listáját.
Ez azt feltételezi, hogy a bemeneti listát növekvő sorrendbe rendezi a rendszer.