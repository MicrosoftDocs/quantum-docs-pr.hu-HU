---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718481"
---
# <a name="andladder-operation"></a>AndLadder művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Felügyelt "és létra" műveletet hajt végre a célként megadott qubits regisztrálásakor.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a>Leírás

Ez a művelet egy átalakítást alkalmaz, amely a következő hozzárendeléssel van elvégezve: számítási alap, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $, ahol $ \ket{x \_ 1, \dots, x \_ n} $ a számítási állapotára hivatkozik `controls` , és ahol $ \ket{y \_ 1, \dots, y \_ {n-1}} $ a számítási állapotára hivatkozik `targets` .

## <a name="input"></a>Bevitel

### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

A CCNOT kapu, amelyet az építkezéshez használni szeretne.


### <a name="controls--qubit"></a>vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A és a létra vezérlőelemként használandó qubits.
Ezzel a művelettel a Invariant állapotú számítási alapú állapotok maradnak `controls` .
A hosszának legalább 2 karakterből kell állnia, és a hosszának meg kell `controls` egyeznie `targets` .


### <a name="targets--qubit"></a>célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A hosszának `targets` legalább 1-nek kell lennie, és meg kell egyeznie a `controls` mínusz egy hosszával.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

- A és a részeként használatos <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> .
- A magyarázathoz és az áramköri diagramhoz lásd a 4,10., 4,3-es szakaszt a Nielsen &.

## <a name="references"></a>Referencia

- [*Michael A. Nielsen, Isaac L.* , a Quantum számítási és a kvantum-információk](http://doi.org/10.1017/CBO9780511976667)