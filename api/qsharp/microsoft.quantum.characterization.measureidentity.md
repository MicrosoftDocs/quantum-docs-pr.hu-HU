---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714970"
---
# <a name="measureidentity-operation"></a>MeasureIdentity művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


Megméri az Identity operátort a qubits-regisztrációban.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Bevitel

### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A mérendő regisztráció.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

Az eredmény értéke `Zero` .

## <a name="remarks"></a>Megjegyzések

Mivel a $ \boldone $ csak a $1 $ sajátérték, és nem rendelkezik negatív sajátérték, ez a művelet mindig visszatér `Zero` , amely a sajátérték $ + 1 = (-1) ^ 0 $ értéknek felel meg, és nem okozza az állapot összeomlását `register` .

Önmagában ez a művelet nem hasznos, de a Process tomográfia környezetében hasznos, mivel információt nyújt a kvantum-folyamat nyomon követésének megőrzéséről.
A veszteséges mérést biztosító célszámítógép például a $ \boldone $ tényleges mérésével helyettesíti ezt a műveletet.