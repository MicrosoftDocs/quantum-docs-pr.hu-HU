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
# <a name="m-operation"></a><span data-ttu-id="c7ce7-102">M művelet</span><span class="sxs-lookup"><span data-stu-id="c7ce7-102">M operation</span></span>

<span data-ttu-id="c7ce7-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c7ce7-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c7ce7-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c7ce7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c7ce7-105">A Pauli $Z $ alapon egyetlen qubit mérését hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="c7ce7-106">A kimeneti eredményt a Distribution \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. adja meg.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="c7ce7-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="c7ce7-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="c7ce7-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c7ce7-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="c7ce7-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c7ce7-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c7ce7-110">A mérendő Qubit.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="c7ce7-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="c7ce7-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="c7ce7-112">`Zero` Ha a $ + $1 sajátérték meg van figyelve, és `One` Ha a $-$1 sajátérték meg van figyelve.</span><span class="sxs-lookup"><span data-stu-id="c7ce7-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7ce7-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c7ce7-113">Remarks</span></span>

<span data-ttu-id="c7ce7-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="c7ce7-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```