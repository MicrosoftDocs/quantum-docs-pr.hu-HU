---
uid: Microsoft.Quantum.Intrinsic.R
title: R-művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 1df4b1197e885e479339e542e8c1ffaeb392543d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818715"
---
# <a name="r-operation"></a><span data-ttu-id="2249d-102">R-művelet</span><span class="sxs-lookup"><span data-stu-id="2249d-102">R operation</span></span>

<span data-ttu-id="2249d-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2249d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2249d-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2249d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2249d-105">A megadott Pauli-tengely elforgatását alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="2249d-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="2249d-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align}, ahol $ \mu \in \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="2249d-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2249d-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2249d-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="2249d-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="2249d-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="2249d-109">A "Pauli" operátor ($ \mu $) exponentiated kell lennie a forgatás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2249d-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="2249d-110">THÉTA: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2249d-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2249d-111">Az a szög, amely alapján a qubit el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="2249d-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="2249d-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2249d-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2249d-113">A Qubit, amelyre a kaput alkalmazni kell.</span><span class="sxs-lookup"><span data-stu-id="2249d-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2249d-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2249d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2249d-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2249d-115">Remarks</span></span>

<span data-ttu-id="2249d-116">A szolgáltatással való híváskor a `pauli = PauliI` művelet *globális szakaszt* alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="2249d-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="2249d-117">Ez a fázis jelentős lehet, ha az elválasztó használatával használja `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="2249d-117">This phase can be significant when used with the `Controlled` functor.</span></span>