---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714704"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="37a9d-102">_ComputeJordanWignerBitString függvény</span><span class="sxs-lookup"><span data-stu-id="37a9d-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="37a9d-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="37a9d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="37a9d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37a9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37a9d-105">A (Z) Jordánia számítási összetevőinek Wigner karakterlánca a Fermion-indexek között egy fermionic-operátorban, amely páros számú létrehozási/megsemmisítő operátorral rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="37a9d-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="37a9d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37a9d-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="37a9d-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37a9d-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37a9d-108">A fermions száma a rendszeren.</span><span class="sxs-lookup"><span data-stu-id="37a9d-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="37a9d-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="37a9d-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="37a9d-110">fermionic operátori indexek.</span><span class="sxs-lookup"><span data-stu-id="37a9d-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="37a9d-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="37a9d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="37a9d-112">Az `Bool[]` a Bitstring, amelybe `true` alkalmazni kell a-t `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="37a9d-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>