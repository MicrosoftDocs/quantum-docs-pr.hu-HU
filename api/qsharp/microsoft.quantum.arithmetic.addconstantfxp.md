---
uid: Microsoft.Quantum.Arithmetic.AddConstantFxP
title: AddConstantFxP művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddConstantFxP
qsharp.summary: Adds a classical constant to a quantum fixed-point number.
ms.openlocfilehash: f6cbdb9ecf316c882dc712749d2d4203136e0070
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191091"
---
# <a name="addconstantfxp-operation"></a><span data-ttu-id="de7cd-102">AddConstantFxP művelet</span><span class="sxs-lookup"><span data-stu-id="de7cd-102">AddConstantFxP operation</span></span>

<span data-ttu-id="de7cd-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="de7cd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="de7cd-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="de7cd-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="de7cd-105">Egy klasszikus állandót hoz létre egy rögzített számú kvantum-ponthoz.</span><span class="sxs-lookup"><span data-stu-id="de7cd-105">Adds a classical constant to a quantum fixed-point number.</span></span>

```qsharp
operation AddConstantFxP (constant : Double, fp : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="de7cd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="de7cd-106">Input</span></span>

### <a name="constant--double"></a><span data-ttu-id="de7cd-107">állandó: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de7cd-107">constant : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="de7cd-108">A kvantum rögzített pont számához hozzáadandó állandó.</span><span class="sxs-lookup"><span data-stu-id="de7cd-108">Constant to add to the quantum fixed-point number.</span></span>


### <a name="fp--fixedpoint"></a><span data-ttu-id="de7cd-109">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="de7cd-109">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="de7cd-110">Az a rögzített pontú szám, amelyhez a konstans hozzá lesz adva.</span><span class="sxs-lookup"><span data-stu-id="de7cd-110">Fixed-point number to which the constant will be added.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de7cd-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de7cd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

