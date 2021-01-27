---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853540"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="1cc89-102">AllowAtMostNCallsCA művelet</span><span class="sxs-lookup"><span data-stu-id="1cc89-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="1cc89-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1cc89-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1cc89-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cc89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cc89-105">A művelet és a adjoint egyik hívása között azt állítja be, hogy egy adott művelet csak bizonyos számú alkalommal legyen meghívva.</span><span class="sxs-lookup"><span data-stu-id="1cc89-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="1cc89-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1cc89-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="1cc89-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1cc89-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1cc89-108">A meghívható maximális számú idő `op` .</span><span class="sxs-lookup"><span data-stu-id="1cc89-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="1cc89-109">op: "TInput =>" TOutput az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="1cc89-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="1cc89-110">Egy művelet, amelynek a hívásait korlátozni kell.</span><span class="sxs-lookup"><span data-stu-id="1cc89-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="1cc89-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1cc89-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1cc89-112">Hiba esetén megjelenítendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="1cc89-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1cc89-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cc89-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1cc89-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1cc89-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="1cc89-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="1cc89-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="1cc89-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="1cc89-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="1cc89-117">Példa</span><span class="sxs-lookup"><span data-stu-id="1cc89-117">Example</span></span>

<span data-ttu-id="1cc89-118">A következő kódrészlet meghiúsul, amikor a rendszer végrehajtja a diagnosztikai szolgáltatást támogató gépeken:</span><span class="sxs-lookup"><span data-stu-id="1cc89-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="1cc89-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1cc89-119">Remarks</span></span>

<span data-ttu-id="1cc89-120">Lehetséges, hogy ezt a műveletet egy nem op-vel rendelkező célok helyettesítik, amelyek nem támogatják azt.</span><span class="sxs-lookup"><span data-stu-id="1cc89-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>