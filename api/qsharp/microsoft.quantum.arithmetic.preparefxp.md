---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 29ba66700db83d0786a70841c7b03843a9ae6219
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222405"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="78902-102">PrepareFxP művelet</span><span class="sxs-lookup"><span data-stu-id="78902-102">PrepareFxP operation</span></span>

<span data-ttu-id="78902-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="78902-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="78902-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="78902-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="78902-105">A kvantum rögzített pont számának inicializálása klasszikus állandó értékre.</span><span class="sxs-lookup"><span data-stu-id="78902-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="78902-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="78902-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="78902-107">állandó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78902-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78902-108">Az állandó, amelyre inicializálni kell a kvantum rögzített pontjának számát.</span><span class="sxs-lookup"><span data-stu-id="78902-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="78902-109">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="78902-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="78902-110">A (FixedPoint típusú) rögzített pontú szám az inicializáláshoz.</span><span class="sxs-lookup"><span data-stu-id="78902-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78902-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78902-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

