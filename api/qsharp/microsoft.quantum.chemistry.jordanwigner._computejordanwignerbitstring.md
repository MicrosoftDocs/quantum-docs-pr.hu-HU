---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839526"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="84137-102">_ComputeJordanWignerBitString függvény</span><span class="sxs-lookup"><span data-stu-id="84137-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="84137-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="84137-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="84137-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="84137-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="84137-105">A (Z) Jordánia számítási összetevőinek Wigner karakterlánca a Fermion-indexek között egy fermionic-operátorban, amely páros számú létrehozási/megsemmisítő operátorral rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="84137-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="84137-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="84137-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="84137-107">nFermions: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84137-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84137-108">A fermions száma a rendszeren.</span><span class="sxs-lookup"><span data-stu-id="84137-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="84137-109">idxFermions: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="84137-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="84137-110">fermionic operátori indexek.</span><span class="sxs-lookup"><span data-stu-id="84137-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="84137-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="84137-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="84137-112">Az `Bool[]` a Bitstring, amelybe `true` alkalmazni kell a-t `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="84137-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="84137-113">Példa</span><span class="sxs-lookup"><span data-stu-id="84137-113">Example</span></span>

<span data-ttu-id="84137-114">let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString: [FALSE, false, false, true, true, true, FALSE].</span><span class="sxs-lookup"><span data-stu-id="84137-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>