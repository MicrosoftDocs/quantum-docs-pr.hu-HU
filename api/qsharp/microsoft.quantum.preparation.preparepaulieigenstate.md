---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193692"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="c15a9-102">PreparePauliEigenstate művelet</span><span class="sxs-lookup"><span data-stu-id="c15a9-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="c15a9-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c15a9-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c15a9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c15a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c15a9-105">Előkészíti a qubit egy adott Pauli-operátor pozitív eigenstate.</span><span class="sxs-lookup"><span data-stu-id="c15a9-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="c15a9-106">Ha az Identity operátor meg van adva, a qubit a maximálisan kevert állapotba kerül elő.</span><span class="sxs-lookup"><span data-stu-id="c15a9-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="c15a9-107">Leírás</span><span class="sxs-lookup"><span data-stu-id="c15a9-107">Description</span></span>

<span data-ttu-id="c15a9-108">Ha a qubit kezdetben a $ \ket {0} $ állapotban van, akkor ez a művelet előkészíti a qubit egy adott Pauli-operátor $ + $1 eigenstate, vagy a esetében, `PauliI` a maximálisan kevert állapotban (lásd: <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="c15a9-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="c15a9-109">Ha a qubit a $ \ket $-tól eltérő állapotban volt {0} , a művelet a következő kapukat alkalmazza: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` és <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="c15a9-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="c15a9-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c15a9-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="c15a9-111">alap: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c15a9-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c15a9-112">Egy Pauli-operátor $P $.</span><span class="sxs-lookup"><span data-stu-id="c15a9-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="c15a9-113">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c15a9-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c15a9-114">Egy előkészített qubit.</span><span class="sxs-lookup"><span data-stu-id="c15a9-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c15a9-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c15a9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

