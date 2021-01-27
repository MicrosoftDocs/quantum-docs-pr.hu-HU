---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842004"
---
# <a name="applyandchain-operation"></a>ApplyAndChain művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kiszámítja a láncot és kapukat

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>Leírás

Explicit módon meg kell adni a kiszámított ideiglenes eredmények kisegítő qubits.
A regisztráció hossza `Length(ctrlRegister) - 2` , ha legalább két vezérlőelem van, ellenkező esetben a hossz 0.

## <a name="input"></a>Bevitel

### <a name="auxregister--qubit"></a>auxRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

