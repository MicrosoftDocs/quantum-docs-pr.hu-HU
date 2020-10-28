---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716581"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="6c45d-102">CControlledA függvény</span><span class="sxs-lookup"><span data-stu-id="6c45d-102">CControlledA function</span></span>

<span data-ttu-id="6c45d-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6c45d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6c45d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c45d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c45d-105">A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz.</span><span class="sxs-lookup"><span data-stu-id="6c45d-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="6c45d-106">Ha `false` nem történik semmi.</span><span class="sxs-lookup"><span data-stu-id="6c45d-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="6c45d-107">A módosító `A` azt jelzi, hogy a művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="6c45d-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="6c45d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6c45d-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="6c45d-109">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="6c45d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6c45d-110">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="6c45d-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="6c45d-111">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="6c45d-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6c45d-112">Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.</span><span class="sxs-lookup"><span data-stu-id="6c45d-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6c45d-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6c45d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6c45d-114">Nem</span><span class="sxs-lookup"><span data-stu-id="6c45d-114">'T</span></span>

<span data-ttu-id="6c45d-115">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6c45d-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c45d-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6c45d-116">See Also</span></span>

- [<span data-ttu-id="6c45d-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="6c45d-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)