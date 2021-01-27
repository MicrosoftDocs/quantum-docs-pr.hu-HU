---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841077"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Vezérlő, cél és segítő qubits elrendezése index szerint

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Leírás

Egy Qubit-tömböt ad vissza, amelynek a célja a 0. index, és az i. index 2. ^ i indexe.  A segítő qubits a tömb összes többi pozíciójában be lesznek helyezve.

## <a name="input"></a>Bevitel

### <a name="controls--qubit"></a>vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>segítő: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

