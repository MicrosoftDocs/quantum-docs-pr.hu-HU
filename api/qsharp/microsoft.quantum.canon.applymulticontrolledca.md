---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209281"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy megfelelően vezérelt művelet szorzás vezérelt verzióját alkalmazza.
A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>singlyControlledOp: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

Egyetlen qubit vezérelt művelet.
A művelet argumentumának első qubit a vezérlőnek kell lennie, és a többi a cél qubits feltételezhető.
`ApplyMultiControlled` mindig legalább 1 argumentummal hívja meg a metódust `singlyControlledOp` .


### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

A vezérelt vezérléssel nem rendelkező kapu, amely az építkezéshez használható.


### <a name="controls--qubit"></a>vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A qubits `singlyControlledOp` .
A hosszának `controls` legalább 1-nek kell lennie.


### <a name="targets--qubit"></a>célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A megcélzott qubits `singlyControlledOp` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ez a művelet csak a tiszta Ancilla-qubits használja.

A magyarázathoz és az áramköri diagramhoz lásd a 4,10., 4,3. szakaszát a Nielsen & a következő ábrán:

## <a name="references"></a>Hivatkozások

- [*Michael A. Nielsen, Isaac L.*, a Quantum számítási és a kvantum-információk](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)