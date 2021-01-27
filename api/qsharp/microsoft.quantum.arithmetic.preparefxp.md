---
uid: Microsoft.Quantum.Arithmetic.PrepareFxP
title: PrepareFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PrepareFxP
qsharp.summary: Initialize a quantum fixed-point number to a classical constant.
ms.openlocfilehash: 31ed1a170a47c77c21aa8b5c291860e422af2e3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845801"
---
# <a name="preparefxp-operation"></a><span data-ttu-id="8e78c-102">PrepareFxP művelet</span><span class="sxs-lookup"><span data-stu-id="8e78c-102">PrepareFxP operation</span></span>

<span data-ttu-id="8e78c-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8e78c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8e78c-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8e78c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8e78c-105">A kvantum rögzített pont számának inicializálása klasszikus állandó értékre.</span><span class="sxs-lookup"><span data-stu-id="8e78c-105">Initialize a quantum fixed-point number to a classical constant.</span></span>

```qsharp
operation PrepareFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8e78c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8e78c-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="8e78c-107">állandó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8e78c-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8e78c-108">Az állandó, amelyre inicializálni kell a kvantum rögzített pontjának számát.</span><span class="sxs-lookup"><span data-stu-id="8e78c-108">Constant to which to initialize the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="8e78c-109">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8e78c-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8e78c-110">A (FixedPoint típusú) rögzített pontú szám az inicializáláshoz.</span><span class="sxs-lookup"><span data-stu-id="8e78c-110">Fixed-point number (of type FixedPoint) to initialize.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e78c-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e78c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

