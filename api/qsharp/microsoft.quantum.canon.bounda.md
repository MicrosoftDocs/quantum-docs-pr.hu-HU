---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216948"
---
# <a name="bounda-function"></a><span data-ttu-id="e0537-102">Bounda függvény</span><span class="sxs-lookup"><span data-stu-id="e0537-102">BoundA function</span></span>

<span data-ttu-id="e0537-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e0537-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e0537-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0537-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0537-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="e0537-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="e0537-106">A módosító `A` azt jelzi, hogy a tömbben lévő összes művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="e0537-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="e0537-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e0537-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="e0537-108">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  []</span><span class="sxs-lookup"><span data-stu-id="e0537-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="e0537-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="e0537-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="e0537-110">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0537-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="e0537-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="e0537-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e0537-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e0537-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0537-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e0537-113">'T</span></span>

<span data-ttu-id="e0537-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="e0537-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0537-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e0537-115">See Also</span></span>

- [<span data-ttu-id="e0537-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="e0537-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)