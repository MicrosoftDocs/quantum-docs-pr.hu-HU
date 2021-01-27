---
uid: Microsoft.Quantum.Intrinsic.M
title: M művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818877"
---
# <a name="m-operation"></a>M művelet

Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


A Pauli $Z $ alapon egyetlen qubit mérését hajtja végre.

A kimeneti eredményt a Distribution \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. adja meg.
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>Bevitel

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

A mérendő Qubit.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

`Zero` Ha a $ + $1 sajátérték meg van figyelve, és `One` Ha a $-$1 sajátérték meg van figyelve.

## <a name="remarks"></a>Megjegyzések

Egyenértékű a következővel:

```qsharp
Measure([PauliZ], [qubit]);
```