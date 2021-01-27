---
uid: Microsoft.Quantum.Intrinsic.H
title: H művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6fa712b00a2745d8c0d8d3198cc9c5e6af3e2400
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818987"
---
# <a name="h-operation"></a><span data-ttu-id="2825c-102">H művelet</span><span class="sxs-lookup"><span data-stu-id="2825c-102">H operation</span></span>

<span data-ttu-id="2825c-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2825c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2825c-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2825c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2825c-105">A Hadamard átalakítását alkalmazza egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="2825c-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="2825c-106">\begin{align} H \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="2825c-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="2825c-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2825c-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2825c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2825c-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="2825c-109">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2825c-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2825c-110">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="2825c-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2825c-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2825c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

