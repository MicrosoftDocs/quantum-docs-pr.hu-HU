---
uid: Microsoft.Quantum.Intrinsic.R
title: R-művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199029"
---
# <a name="r-operation"></a><span data-ttu-id="0cd7c-102">R-művelet</span><span class="sxs-lookup"><span data-stu-id="0cd7c-102">R operation</span></span>

<span data-ttu-id="0cd7c-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0cd7c-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0cd7c-105">A megadott Pauli-tengely elforgatását alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="0cd7c-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align}, ahol $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0cd7c-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0cd7c-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="0cd7c-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="0cd7c-109">A "Pauli" operátor ($ \mu $) exponentiated kell lennie a forgatás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="0cd7c-110">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0cd7c-111">Az a szög, amely alapján a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="0cd7c-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0cd7c-113">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0cd7c-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0cd7c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0cd7c-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="0cd7c-115">Remarks</span></span>

<span data-ttu-id="0cd7c-116">A szolgáltatással való híváskor a `pauli = PauliI` művelet *globális szakaszt* alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="0cd7c-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="0cd7c-117">Ez a fázis jelentős lehet, ha az elválasztó használatával használja `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="0cd7c-117">This phase can be significant when used with the `Controlled` functor.</span></span>