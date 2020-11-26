---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202566"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="55f7a-102">AllowAtMostNCallsCA művelet</span><span class="sxs-lookup"><span data-stu-id="55f7a-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="55f7a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="55f7a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="55f7a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55f7a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55f7a-105">A művelet és a adjoint egyik hívása között azt állítja be, hogy egy adott művelet csak bizonyos számú alkalommal legyen meghívva.</span><span class="sxs-lookup"><span data-stu-id="55f7a-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="55f7a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="55f7a-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="55f7a-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55f7a-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55f7a-108">A meghívható maximális számú idő `op` .</span><span class="sxs-lookup"><span data-stu-id="55f7a-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="55f7a-109">op: "TInput =>" TOutput az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="55f7a-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="55f7a-110">Egy művelet, amelynek a hívásait korlátozni kell.</span><span class="sxs-lookup"><span data-stu-id="55f7a-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="55f7a-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="55f7a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="55f7a-112">Hiba esetén megjelenítendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="55f7a-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55f7a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55f7a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55f7a-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="55f7a-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="55f7a-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="55f7a-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="55f7a-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="55f7a-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="55f7a-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="55f7a-117">Remarks</span></span>

<span data-ttu-id="55f7a-118">Lehetséges, hogy ezt a műveletet egy nem op-vel rendelkező célok helyettesítik, amelyek nem támogatják azt.</span><span class="sxs-lookup"><span data-stu-id="55f7a-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>