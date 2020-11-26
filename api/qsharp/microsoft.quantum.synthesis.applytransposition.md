---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203314"
---
# <a name="applytransposition-operation"></a>ApplyTransposition művelet

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

Ez a művelet felcseréli az amplitúdót az indexben `a` az amplitúdónál az indexnél az `b` adott állapotú, `register` $n $ hosszúságú vektorban.  Ha `a` egyenlő `b` , az állapot-vektor nem módosul.

## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

Első index (0 és $2 ^ n-$1 közötti értéknek kell lennie)


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

Második index (0 és $2 ^ n-$1 közötti értéknek kell lennie)


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$N $ qubits listája, amelyre az átültetést alkalmazza a rendszer.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

