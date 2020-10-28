---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 6d2ead95a60ed3cc8ee95fb7f91e1aa49d366a48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711680"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace művelet

Névtér: [Microsoft. Quantum. Extensions. Testing](xref:Microsoft.Quantum.Extensions.Testing)

Csomag [](https://nuget.org/packages/)


> [!WARNING]
> A AssertOperationsEqualInPlace elavult. Használja <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> helyette.
>
> Használja a következőt: @"microsoft.quantum.diagnostics.assertoperationsequalinplace".
> Vegye figyelembe, hogy a művelet argumentumai sorrendje megváltozott.



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>Bevitel

### <a name="actual--qubit--unit"></a>tényleges: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) 




### <a name="expected--qubit--unit-adj"></a>várt: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj




### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

