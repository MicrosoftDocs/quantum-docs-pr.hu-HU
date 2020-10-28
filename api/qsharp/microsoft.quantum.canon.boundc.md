---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716665"
---
# <a name="boundc-function"></a><span data-ttu-id="372d3-102">BoundC függvény</span><span class="sxs-lookup"><span data-stu-id="372d3-102">BoundC function</span></span>

<span data-ttu-id="372d3-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="372d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="372d3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="372d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="372d3-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="372d3-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="372d3-106">A módosító `C` azt jelzi, hogy a tömbben lévő összes művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="372d3-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="372d3-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="372d3-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="372d3-108">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL []</span><span class="sxs-lookup"><span data-stu-id="372d3-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="372d3-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="372d3-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="372d3-110">Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="372d3-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="372d3-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="372d3-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="372d3-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="372d3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="372d3-113">Nem</span><span class="sxs-lookup"><span data-stu-id="372d3-113">'T</span></span>

<span data-ttu-id="372d3-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="372d3-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="372d3-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="372d3-115">See Also</span></span>

- [<span data-ttu-id="372d3-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="372d3-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)