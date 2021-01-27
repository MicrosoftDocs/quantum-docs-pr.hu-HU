---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841713"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A megadott qubit csak akkor áll le, ha mindkét vezérlő qubits 1 állapotban van, a T-depth 1 értékkel, a adjoint művelet elvégzéséhez használja a mérést.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

`target`A csak akkor áll le, ha mindkét vezérlő 1, de feltételezi, hogy `target` a 0 állapotban van.  A műveletnek T-Count 4, T-depth 1, és egy segítő qubit van szüksége, ezért érdemes lehet egy CCNOT-műveletnek lennie, ha `target` az ismert értéke 0.  A művelet adjoint a mérésen alapul, és nem igényel T-kaput, és nincs segítő qubit.

## <a name="input"></a>Bevitel

### <a name="control1--qubit"></a>control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Első vezérlő qubit


### <a name="control2--qubit"></a>2. vezérlőelem: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Második vezérlő qubit


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Cél kiegészítő qubit; a kötelező állapot 0



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Hivatkozások

- Cody Jones: "új konstrukciók a hibatűrő Toffoli kapuhoz", leltár. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) Doi: 10.1103/PhysRevA. 87.022328
- Peter Selinger: "T-depthal One", leltár. Rev. A 87, 042302, 2013 [arXiv: 1210.0974](https://arxiv.org/abs/1210.0974) Doi: 10.1103/PhysRevA. 87.042302