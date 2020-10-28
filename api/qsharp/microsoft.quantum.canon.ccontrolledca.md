---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716567"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="ece28-102">CControlledCA függvény</span><span class="sxs-lookup"><span data-stu-id="ece28-102">CControlledCA function</span></span>

<span data-ttu-id="ece28-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ece28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ece28-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ece28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ece28-105">A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz.</span><span class="sxs-lookup"><span data-stu-id="ece28-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="ece28-106">Ha `false` nem történik semmi.</span><span class="sxs-lookup"><span data-stu-id="ece28-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="ece28-107">A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="ece28-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="ece28-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ece28-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="ece28-109">op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="ece28-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="ece28-110">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="ece28-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="ece28-111">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="ece28-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="ece28-112">Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.</span><span class="sxs-lookup"><span data-stu-id="ece28-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ece28-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ece28-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ece28-114">Nem</span><span class="sxs-lookup"><span data-stu-id="ece28-114">'T</span></span>

<span data-ttu-id="ece28-115">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="ece28-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ece28-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ece28-116">See Also</span></span>

- [<span data-ttu-id="ece28-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="ece28-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)