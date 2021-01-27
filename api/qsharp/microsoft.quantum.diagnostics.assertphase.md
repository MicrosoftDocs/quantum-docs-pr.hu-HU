---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830083"
---
# <a name="assertphase-operation"></a><span data-ttu-id="cab1d-102">AssertPhase művelet</span><span class="sxs-lookup"><span data-stu-id="cab1d-102">AssertPhase operation</span></span>

<span data-ttu-id="cab1d-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cab1d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cab1d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cab1d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cab1d-105">Azt állítja be, hogy az egyenlő prioritású állapot fázisában a várt érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="cab1d-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="cab1d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="cab1d-106">Description</span></span>

<span data-ttu-id="cab1d-107">Ez a művelet azt állítja be, hogy a $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ ket {0} + e ^ {-i\phi} \ ket) $t $ értékű Quantum állapot $ \phi $ {1} értéke a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="cab1d-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="cab1d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cab1d-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="cab1d-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cab1d-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cab1d-110">A várt érték: $ \phi \in (-\pi, \pi] $.</span><span class="sxs-lookup"><span data-stu-id="cab1d-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="cab1d-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cab1d-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cab1d-112">A várt állapotot tároló qubit.</span><span class="sxs-lookup"><span data-stu-id="cab1d-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="cab1d-113">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cab1d-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cab1d-114">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="cab1d-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cab1d-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cab1d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="cab1d-116">Példa</span><span class="sxs-lookup"><span data-stu-id="cab1d-116">Example</span></span>

<span data-ttu-id="cab1d-117">A következő érvényesítés sikeres: `qubit` állapot $ \ket{\psi} = e ^ {i 0.5} \ SQRT {1/2} \ ket {0} + e ^ {i 0.5} \ SQRT {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="cab1d-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="cab1d-118">`qubit` állapotban van $ \ket{\psi} = e ^ {i 0.5} \ SQRT {1/2} \ ket {0} + e ^ {-i 0.5} \ SQRT {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="cab1d-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="cab1d-119">`qubit` állapotban van $ \ket{\psi} = e ^ {-i 2.2} \ SQRT {1/2} \ ket {0} + e ^ {i 0.2} \ SQRT {1/2} \ ket {1} $;</span><span class="sxs-lookup"><span data-stu-id="cab1d-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`