---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: 4443af5884755f72fac6f9b76f95c3831c67b13f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207173"
---
# <a name="decomposeintotimestepsca-function"></a>DecomposeIntoTimeStepsCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> A DecomposeIntoTimeStepsCA elavult. Használja <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> helyette.



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit--is-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL




### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit--is-adj--ctl"></a>Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

