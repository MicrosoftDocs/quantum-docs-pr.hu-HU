---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851972"
---
# <a name="weightonepaulis-function"></a>WeightOnePaulis függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az összes Weight-1 Pauli operátor tömbjét adja vissza egy adott számú qubits.

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a visszaadott Pauli-operátorok vannak meghatározva.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Több qubit Pauli-operátorok tömbje, amelyek mindegyike egy hosszúságú tömbként van ábrázolva `nQubits` .