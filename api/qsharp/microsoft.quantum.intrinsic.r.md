---
uid: Microsoft.Quantum.Intrinsic.R
title: R-művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720929"
---
# <a name="r-operation"></a><span data-ttu-id="9662f-102">R-művelet</span><span class="sxs-lookup"><span data-stu-id="9662f-102">R operation</span></span>

<span data-ttu-id="9662f-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="9662f-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="9662f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9662f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9662f-105">A megadott Pauli-tengely elforgatását alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="9662f-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="9662f-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align}, ahol $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="9662f-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9662f-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9662f-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="9662f-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9662f-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9662f-109">A "Pauli" operátor ($ \mu $) exponentiated kell lennie a forgatás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="9662f-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="9662f-110">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9662f-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9662f-111">Az a szög, amely alapján a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="9662f-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="9662f-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9662f-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9662f-113">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="9662f-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9662f-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9662f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9662f-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9662f-115">Remarks</span></span>

<span data-ttu-id="9662f-116">A szolgáltatással való híváskor a `pauli = PauliI` művelet *globális szakaszt* alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="9662f-116">When called with `pauli = PauliI`, this operation applies a *global phase* .</span></span> <span data-ttu-id="9662f-117">Ez a fázis jelentős lehet, ha az elválasztó használatával használja `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="9662f-117">This phase can be significant when used with the `Controlled` functor.</span></span>