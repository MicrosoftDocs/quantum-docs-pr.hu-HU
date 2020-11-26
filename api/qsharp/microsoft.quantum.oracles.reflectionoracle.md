---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226655"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="da465-102">ReflectionOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="da465-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="da465-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="da465-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="da465-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da465-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da465-105">Egy reflexiós Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="da465-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="da465-106">A reflexiós Oracle, $O $, bemenetekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="da465-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="da465-107">A $ \phi $ fázis, amelyből el kell forgatni a tükrözt alterületet.</span><span class="sxs-lookup"><span data-stu-id="da465-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="da465-108">A qubit regisztrálnia kell a megadott reflexió végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="da465-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="da465-109">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="da465-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="da465-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="da465-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="da465-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="da465-111">Remarks</span></span>

<span data-ttu-id="da465-112">Ez az Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ egy részleges tükröződést végez egy $ \phi $ fázissal, amely egyetlen tiszta állapotot ($ \ket{\psi} $) mutat.</span><span class="sxs-lookup"><span data-stu-id="da465-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>