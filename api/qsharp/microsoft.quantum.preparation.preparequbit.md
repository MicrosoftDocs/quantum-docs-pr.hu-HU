---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723010"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="e05ee-102">PrepareQubit művelet</span><span class="sxs-lookup"><span data-stu-id="e05ee-102">PrepareQubit operation</span></span>

<span data-ttu-id="e05ee-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e05ee-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e05ee-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e05ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e05ee-105">Előkészíti a qubit a megadott Pauli-operátor + 1 ( `Zero` ) eigenstate.</span><span class="sxs-lookup"><span data-stu-id="e05ee-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="e05ee-106">Ha az Identity operátor meg van adva, a qubit a maximálisan kevert állapotba kerül elő.</span><span class="sxs-lookup"><span data-stu-id="e05ee-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="e05ee-107">Ha a qubit kezdetben a $ \ket {0} $ állapotban van, akkor ez a művelet előkészíti a qubit egy adott Pauli-operátor $ + $1 eigenstate, vagy a esetében, `PauliI` a maximálisan kevert állapotban (lásd: <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="e05ee-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="e05ee-108">Ha a qubit a $ \ket $-tól eltérő állapotban volt {0} , a művelet a következő kapukat alkalmazza: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` és <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="e05ee-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e05ee-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e05ee-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="e05ee-110">alap: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="e05ee-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="e05ee-111">Egy Pauli-operátor $P $.</span><span class="sxs-lookup"><span data-stu-id="e05ee-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="e05ee-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e05ee-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e05ee-113">Egy előkészített qubit.</span><span class="sxs-lookup"><span data-stu-id="e05ee-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e05ee-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e05ee-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

