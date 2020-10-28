---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716329"
---
# <a name="decomposeintotimestepsca-function"></a>DecomposeIntoTimeStepsCA függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


> [!WARNING]
> A DecomposeIntoTimeStepsCA elavult. Használja <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> helyette.



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Bevitel

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit-adj--ctl"></a>op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL




### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit-adj--ctl"></a>Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

