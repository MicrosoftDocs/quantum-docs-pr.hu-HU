---
uid: Microsoft.Quantum.Intrinsic.T
title: T művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198401"
---
# <a name="t-operation"></a><span data-ttu-id="4fa42-102">T művelet</span><span class="sxs-lookup"><span data-stu-id="4fa42-102">T operation</span></span>

<span data-ttu-id="4fa42-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4fa42-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4fa42-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4fa42-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4fa42-105">A T-kaput alkalmazza egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="4fa42-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4fa42-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4fa42-106">Description</span></span>

<span data-ttu-id="4fa42-107">Ezt a műveletet szimulálhatja az egységes mátrix \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4fa42-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="4fa42-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4fa42-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="4fa42-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4fa42-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="4fa42-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4fa42-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4fa42-111">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="4fa42-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fa42-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fa42-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

