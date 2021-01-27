---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: e6a88ccf4c01b2f0a7344e3823b2748790cf9650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854341"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="271d6-102">PrepareQubit művelet</span><span class="sxs-lookup"><span data-stu-id="271d6-102">PrepareQubit operation</span></span>

<span data-ttu-id="271d6-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="271d6-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="271d6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="271d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="271d6-105">A PrepareQubit elavult.</span><span class="sxs-lookup"><span data-stu-id="271d6-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="271d6-106">Használja <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> helyette.</span><span class="sxs-lookup"><span data-stu-id="271d6-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="271d6-107">Előkészíti a qubit a megadott Pauli-operátor + 1 ( `Zero` ) eigenstate.</span><span class="sxs-lookup"><span data-stu-id="271d6-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="271d6-108">Ha az Identity operátor meg van adva, a qubit a maximálisan kevert állapotba kerül elő.</span><span class="sxs-lookup"><span data-stu-id="271d6-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="271d6-109">Ha a qubit kezdetben a $ \ket {0} $ állapotban van, akkor ez a művelet előkészíti a qubit egy adott Pauli-operátor $ + $1 eigenstate, vagy a esetében, `PauliI` a maximálisan kevert állapotban (lásd: <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="271d6-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="271d6-110">Ha a qubit a $ \ket $-tól eltérő állapotban volt {0} , a művelet a következő kapukat alkalmazza: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` és <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="271d6-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="271d6-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="271d6-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="271d6-112">alap: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="271d6-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="271d6-113">Egy Pauli-operátor $P $.</span><span class="sxs-lookup"><span data-stu-id="271d6-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="271d6-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="271d6-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="271d6-115">Egy előkészített qubit.</span><span class="sxs-lookup"><span data-stu-id="271d6-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="271d6-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="271d6-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

