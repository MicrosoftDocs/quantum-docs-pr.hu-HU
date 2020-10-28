---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724886"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="894e3-102">PrepareSingleQubitIdentity művelet</span><span class="sxs-lookup"><span data-stu-id="894e3-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="894e3-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="894e3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="894e3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="894e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="894e3-105">Qubit előkészítése a maximálisan kevert állapotban.</span><span class="sxs-lookup"><span data-stu-id="894e3-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="894e3-106">Előkészíti a megadott qubit a $ \boldone/$2 állapotban a depolarizációs csatorna $ $ \begin{align} \Omega (\rho) \mathrel{alkalmazásával: =} \frac {1} {4} \ sum_ {\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $, ahol a $ \sigma \_ i $ a $i $ th Pauli operátor, ahol a $ \rho $ egy vegyes állapotot jelölő sűrűségű operátor.</span><span class="sxs-lookup"><span data-stu-id="894e3-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="894e3-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="894e3-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="894e3-108">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="894e3-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="894e3-109">Egy qubit, amelynek állapotát a fent leírt módon kell leállítani.</span><span class="sxs-lookup"><span data-stu-id="894e3-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="894e3-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="894e3-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="894e3-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="894e3-111">Remarks</span></span>

<span data-ttu-id="894e3-112">A vegyes állapotú $ \boldone/$2 azt írja le, hogy a művelet egy adott állapotra való alkalmazásának eredményét implicit módon mutatja-e be a műveletben végrehajtott véletlenszerű választási lehetőség.</span><span class="sxs-lookup"><span data-stu-id="894e3-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="894e3-113">Így egyetlen alkalmazás esetében a művelet leképezi a tiszta állapotokat a tiszta állapotokra, de a várt módon működik.</span><span class="sxs-lookup"><span data-stu-id="894e3-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="894e3-114">Ez a művelet a Process tomográfia szolgáltatásban használható a csatorna *nem egységes* összetevőinek mérésére.</span><span class="sxs-lookup"><span data-stu-id="894e3-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>