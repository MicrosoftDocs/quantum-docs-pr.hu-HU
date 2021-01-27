---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851811"
---
# <a name="measureidentity-operation"></a>MeasureIdentity művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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