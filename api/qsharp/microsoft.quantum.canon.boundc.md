---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207581"
---
# <a name="boundc-function"></a><span data-ttu-id="e13d7-102">BoundC függvény</span><span class="sxs-lookup"><span data-stu-id="e13d7-102">BoundC function</span></span>

<span data-ttu-id="e13d7-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e13d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e13d7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e13d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e13d7-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="e13d7-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="e13d7-106">A módosító `C` azt jelzi, hogy a tömbben lévő összes művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="e13d7-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="e13d7-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e13d7-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="e13d7-108">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL []</span><span class="sxs-lookup"><span data-stu-id="e13d7-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="e13d7-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="e13d7-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="e13d7-110">Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="e13d7-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="e13d7-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="e13d7-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e13d7-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e13d7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e13d7-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e13d7-113">'T</span></span>

<span data-ttu-id="e13d7-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="e13d7-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="e13d7-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e13d7-115">See Also</span></span>

- [<span data-ttu-id="e13d7-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="e13d7-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)