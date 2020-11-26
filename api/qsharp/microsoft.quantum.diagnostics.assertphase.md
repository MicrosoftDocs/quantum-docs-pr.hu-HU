---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202260"
---
# <a name="assertphase-operation"></a><span data-ttu-id="81a78-102">AssertPhase művelet</span><span class="sxs-lookup"><span data-stu-id="81a78-102">AssertPhase operation</span></span>

<span data-ttu-id="81a78-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="81a78-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="81a78-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81a78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81a78-105">Azt állítja be, hogy az egyenlő prioritású állapot fázisában a várt érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="81a78-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="81a78-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="81a78-106">Description</span></span>

<span data-ttu-id="81a78-107">Ez a művelet azt állítja be, hogy a $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket) $t $ értékű Quantum állapot $ \phi $ {1} értéke a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="81a78-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="81a78-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="81a78-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="81a78-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81a78-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81a78-110">A várt érték: $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="81a78-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="81a78-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="81a78-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="81a78-112">A várt állapotot tároló qubit.</span><span class="sxs-lookup"><span data-stu-id="81a78-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="81a78-113">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="81a78-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="81a78-114">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="81a78-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81a78-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81a78-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

