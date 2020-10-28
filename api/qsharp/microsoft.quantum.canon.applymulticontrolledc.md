---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 36010ba667190c237b64f60b7246010199a8ba1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717967"
---
# <a name="applymulticontrolledc-operation"></a>ApplyMultiControlledC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy megfelelően vezérelt művelet szorzás vezérelt verzióját alkalmazza.
A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egyetlen qubit vezérelt művelet.
A művelet argumentumának első qubit a vezérlőnek kell lennie, a többi pedig a célként megadott qubits.
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

## <a name="references"></a>Referencia

- [*Michael A. Nielsen, Isaac L.* , a Quantum számítási és a kvantum-információk](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)