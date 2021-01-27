---
uid: Microsoft.Quantum.Arithmetic.AddConstantFxP
title: AddConstantFxP művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddConstantFxP
qsharp.summary: Adds a classical constant to a quantum fixed-point number.
ms.openlocfilehash: fd985d1112298c3d2bbb0db2ff0d934098566e93
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843885"
---
# <a name="addconstantfxp-operation"></a><span data-ttu-id="56373-102">AddConstantFxP művelet</span><span class="sxs-lookup"><span data-stu-id="56373-102">AddConstantFxP operation</span></span>

<span data-ttu-id="56373-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="56373-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="56373-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="56373-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="56373-105">Egy klasszikus állandót hoz létre egy rögzített számú kvantum-ponthoz.</span><span class="sxs-lookup"><span data-stu-id="56373-105">Adds a classical constant to a quantum fixed-point number.</span></span>

```qsharp
operation AddConstantFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="56373-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="56373-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="56373-107">állandó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="56373-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="56373-108">A kvantum rögzített pont számához hozzáadandó állandó.</span><span class="sxs-lookup"><span data-stu-id="56373-108">Constant to add to the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="56373-109">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="56373-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="56373-110">Az a rögzített pontú szám, amelyhez a konstans hozzá lesz adva.</span><span class="sxs-lookup"><span data-stu-id="56373-110">Fixed-point number to which the constant will be added.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56373-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56373-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

