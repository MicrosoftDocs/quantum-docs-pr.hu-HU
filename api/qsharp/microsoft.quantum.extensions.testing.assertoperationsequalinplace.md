---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace művelet
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 64cc1e5c78af100b652ced24f00f3097c35ea5d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98820239"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace művelet

Névtér: [Microsoft. Quantum. Extensions. Testing](xref:Microsoft.Quantum.Extensions.Testing)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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




### <a name="expected--qubit--unit--is-adj"></a>várt: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)




### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

