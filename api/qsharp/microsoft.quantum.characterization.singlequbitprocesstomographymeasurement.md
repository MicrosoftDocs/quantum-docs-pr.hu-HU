---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714928"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>SingleQubitProcessTomographyMeasurement művelet

Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)

Csomag [](https://nuget.org/packages/)


Egy qubit-alapú Process tomográfia-mérést hajt végre Pauli alapon, egy adott érdeklődési csatornán keresztül.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Bevitel

### <a name="preparation--pauli"></a>előkészítés: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A Pauli-alapú elem $P $, amelyben a qubit elő kell készíteni.


### <a name="measurement--pauli"></a>mérés: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A Pauli-alapú elem $Q $, amelyben a qubit mérni kell.


### <a name="channel--qubit--unit"></a>csatorna: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egyetlen qubit-csatorna $ \Lambda $, amelynek viselkedését a Process tomográfia becsüli.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

Az eredmény a `Zero` következő valószínűséggel: $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Megjegyzések

A művelet által visszaadott eredmények eloszlása a qubit állami tomográfia különleges esete. Engedje, hogy a $ \rho = J (\Lambda)/$2 legyen a Choi – Jamiłkowski ($ \Lambda $) állapot. Ezután a fenti eloszlás megegyezik a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $, ahol a $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 a $P $ és $Q $ értéknek megfelelő tényleges mérés.