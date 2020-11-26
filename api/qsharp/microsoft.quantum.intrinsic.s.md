---
uid: Microsoft.Quantum.Intrinsic.S
title: S művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: c697408c4efe1963787b5aee8f0d3bb6b9e64dd5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198452"
---
# <a name="s-operation"></a><span data-ttu-id="5beac-102">S művelet</span><span class="sxs-lookup"><span data-stu-id="5beac-102">S operation</span></span>

<span data-ttu-id="5beac-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5beac-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5beac-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5beac-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5beac-105">A S kaput egyetlen qubit alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="5beac-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5beac-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="5beac-106">Description</span></span>

<span data-ttu-id="5beac-107">Ezt a műveletet szimulálhatja az egységes mátrix \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="5beac-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="5beac-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5beac-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="5beac-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5beac-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="5beac-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5beac-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5beac-111">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="5beac-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5beac-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5beac-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

