---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724214"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="01075-102">ReflectionOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="01075-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="01075-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="01075-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="01075-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01075-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01075-105">Egy reflexiós Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="01075-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="01075-106">A reflexiós Oracle, $O $, bemenetekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="01075-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="01075-107">A $ \phi $ fázis, amelyből el kell forgatni a tükrözt alterületet.</span><span class="sxs-lookup"><span data-stu-id="01075-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="01075-108">A qubit regisztrálnia kell a megadott reflexió végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="01075-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="01075-109">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="01075-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="01075-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="01075-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="01075-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="01075-111">Remarks</span></span>

<span data-ttu-id="01075-112">Ez az Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ egy részleges tükröződést végez egy $ \phi $ fázissal, amely egyetlen tiszta állapotot ($ \ket{\psi} $) mutat.</span><span class="sxs-lookup"><span data-stu-id="01075-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>