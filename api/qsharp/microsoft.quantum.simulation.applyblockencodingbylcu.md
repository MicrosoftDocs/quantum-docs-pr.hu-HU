---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722128"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU művelet

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag [](https://nuget.org/packages/)


A implementálása `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Bevitel

### <a name="statepreparation--t--unit-adj--ctl"></a>statePreparation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL




### <a name="selector--ts--unit-adj--ctl"></a>választó: ('T, 'S) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL




### <a name="auxiliary--t"></a>kiegészítő: nem




### <a name="system--s"></a>System: 'S





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="s"></a>Képgalériája

