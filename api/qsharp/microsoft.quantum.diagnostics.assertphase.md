---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712954"
---
# <a name="assertphase-operation"></a><span data-ttu-id="6f295-102">AssertPhase művelet</span><span class="sxs-lookup"><span data-stu-id="6f295-102">AssertPhase operation</span></span>

<span data-ttu-id="6f295-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6f295-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6f295-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6f295-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6f295-105">Azt állítja be, hogy az egyenlő prioritású állapot fázisában a várt érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="6f295-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="6f295-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6f295-106">Description</span></span>

<span data-ttu-id="6f295-107">Ez a művelet azt állítja be, hogy a $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket) $t $ értékű Quantum állapot $ \phi $ {1} értéke a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="6f295-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="6f295-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6f295-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="6f295-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f295-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f295-110">A várt érték: $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="6f295-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="6f295-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6f295-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6f295-112">A várt állapotot tároló qubit.</span><span class="sxs-lookup"><span data-stu-id="6f295-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="6f295-113">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f295-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f295-114">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="6f295-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f295-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f295-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

