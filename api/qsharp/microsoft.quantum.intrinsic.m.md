---
uid: Microsoft.Quantum.Intrinsic.M
title: M művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212341"
---
# <a name="m-operation"></a><span data-ttu-id="fcc83-102">M művelet</span><span class="sxs-lookup"><span data-stu-id="fcc83-102">M operation</span></span>

<span data-ttu-id="fcc83-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="fcc83-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="fcc83-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fcc83-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fcc83-105">A Pauli $Z $ alapon egyetlen qubit mérését hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="fcc83-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="fcc83-106">A kimeneti eredményt a Distribution \begin{align} \Pr (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. adja meg.</span><span class="sxs-lookup"><span data-stu-id="fcc83-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="fcc83-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fcc83-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="fcc83-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fcc83-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="fcc83-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="fcc83-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="fcc83-110">A mérendő Qubit.</span><span class="sxs-lookup"><span data-stu-id="fcc83-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="fcc83-111">Kimenet: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="fcc83-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="fcc83-112">`Zero` Ha a $ + $1 sajátérték meg van figyelve, és `One` Ha a $-$1 sajátérték meg van figyelve.</span><span class="sxs-lookup"><span data-stu-id="fcc83-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcc83-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fcc83-113">Remarks</span></span>

<span data-ttu-id="fcc83-114">Egyenértékű a következővel:</span><span class="sxs-lookup"><span data-stu-id="fcc83-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```