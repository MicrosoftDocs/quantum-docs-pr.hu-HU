---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716748"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


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

