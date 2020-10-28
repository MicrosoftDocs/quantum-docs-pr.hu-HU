---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716636"
---
# <a name="boundca-function"></a><span data-ttu-id="348f9-102">BoundCA függvény</span><span class="sxs-lookup"><span data-stu-id="348f9-102">BoundCA function</span></span>

<span data-ttu-id="348f9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="348f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="348f9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="348f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="348f9-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="348f9-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="348f9-106">A módosító `CA` azt jelzi, hogy a tömbben lévő összes művelet adjointable és ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="348f9-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="348f9-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="348f9-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="348f9-108">műveletek: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="348f9-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="348f9-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="348f9-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="348f9-110">Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="348f9-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="348f9-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="348f9-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="348f9-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="348f9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="348f9-113">Nem</span><span class="sxs-lookup"><span data-stu-id="348f9-113">'T</span></span>

<span data-ttu-id="348f9-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="348f9-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="348f9-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="348f9-115">See Also</span></span>

- [<span data-ttu-id="348f9-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="348f9-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)