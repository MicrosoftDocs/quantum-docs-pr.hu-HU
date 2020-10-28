---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716594"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="c2c9a-102">CControlled függvény</span><span class="sxs-lookup"><span data-stu-id="c2c9a-102">CControlled function</span></span>

<span data-ttu-id="c2c9a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2c9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2c9a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2c9a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2c9a-105">A művelet op esetében egy új műveletet ad vissza, amely az op-t alkalmazza, ha a klasszikus vezérlőelem-bit igaz.</span><span class="sxs-lookup"><span data-stu-id="c2c9a-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="c2c9a-106">Ha `false` nem történik semmi.</span><span class="sxs-lookup"><span data-stu-id="c2c9a-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="c2c9a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c2c9a-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="c2c9a-108">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2c9a-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c2c9a-109">Egy feltételesen alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="c2c9a-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="c2c9a-110">Kimenet: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2c9a-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c2c9a-111">Egy új művelet, amely az op, ha a klasszikus vezérlő bit igaz.</span><span class="sxs-lookup"><span data-stu-id="c2c9a-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c2c9a-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c2c9a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2c9a-113">Nem</span><span class="sxs-lookup"><span data-stu-id="c2c9a-113">'T</span></span>

<span data-ttu-id="c2c9a-114">A feltételesen alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="c2c9a-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2c9a-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c2c9a-115">See Also</span></span>

- [<span data-ttu-id="c2c9a-116">Microsoft. Quantum. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="c2c9a-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="c2c9a-117">Microsoft. Quantum. Canon. CControlledA</span><span class="sxs-lookup"><span data-stu-id="c2c9a-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="c2c9a-118">Microsoft. Quantum. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="c2c9a-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)