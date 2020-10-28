---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e5975455385e182236d7e2864e26ca00795a40c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716580"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="729ac-102">CControlledC függvény</span><span class="sxs-lookup"><span data-stu-id="729ac-102">CControlledC function</span></span>

<span data-ttu-id="729ac-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="729ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="729ac-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="729ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="729ac-105">A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz.</span><span class="sxs-lookup"><span data-stu-id="729ac-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="729ac-106">Ha `false` nem történik semmi.</span><span class="sxs-lookup"><span data-stu-id="729ac-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="729ac-107">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="729ac-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="729ac-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="729ac-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="729ac-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="729ac-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="729ac-110">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="729ac-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl"></a><span data-ttu-id="729ac-111">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="729ac-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="729ac-112">Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.</span><span class="sxs-lookup"><span data-stu-id="729ac-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="729ac-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="729ac-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="729ac-114">Nem</span><span class="sxs-lookup"><span data-stu-id="729ac-114">'T</span></span>

<span data-ttu-id="729ac-115">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="729ac-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="729ac-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="729ac-116">See Also</span></span>

- [<span data-ttu-id="729ac-117">Microsoft. Quantum. Canon. CControlled</span><span class="sxs-lookup"><span data-stu-id="729ac-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)