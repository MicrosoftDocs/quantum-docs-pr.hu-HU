---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844545"
---
# <a name="bounda-function"></a><span data-ttu-id="91d6f-102">Bounda függvény</span><span class="sxs-lookup"><span data-stu-id="91d6f-102">BoundA function</span></span>

<span data-ttu-id="91d6f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91d6f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91d6f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91d6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91d6f-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="91d6f-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="91d6f-106">A módosító `A` azt jelzi, hogy a tömbben lévő összes művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="91d6f-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="91d6f-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="91d6f-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="91d6f-108">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  []</span><span class="sxs-lookup"><span data-stu-id="91d6f-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="91d6f-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="91d6f-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="91d6f-110">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91d6f-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="91d6f-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="91d6f-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91d6f-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="91d6f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91d6f-113">Nem</span><span class="sxs-lookup"><span data-stu-id="91d6f-113">'T</span></span>

<span data-ttu-id="91d6f-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="91d6f-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="91d6f-115">Példa</span><span class="sxs-lookup"><span data-stu-id="91d6f-115">Example</span></span>

<span data-ttu-id="91d6f-116">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="91d6f-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="91d6f-117">és</span><span class="sxs-lookup"><span data-stu-id="91d6f-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="91d6f-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="91d6f-118">See Also</span></span>

- [<span data-ttu-id="91d6f-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="91d6f-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)