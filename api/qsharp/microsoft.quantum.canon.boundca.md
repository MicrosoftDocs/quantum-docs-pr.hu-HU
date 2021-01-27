---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844533"
---
# <a name="boundca-function"></a><span data-ttu-id="ee243-102">BoundCA függvény</span><span class="sxs-lookup"><span data-stu-id="ee243-102">BoundCA function</span></span>

<span data-ttu-id="ee243-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee243-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee243-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee243-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee243-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="ee243-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ee243-106">A módosító `CA` azt jelzi, hogy a tömbben lévő összes művelet adjointable és ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="ee243-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ee243-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ee243-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="ee243-108">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="ee243-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="ee243-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="ee243-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="ee243-110">Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="ee243-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ee243-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="ee243-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ee243-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ee243-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee243-113">Nem</span><span class="sxs-lookup"><span data-stu-id="ee243-113">'T</span></span>

<span data-ttu-id="ee243-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="ee243-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="ee243-115">Példa</span><span class="sxs-lookup"><span data-stu-id="ee243-115">Example</span></span>

<span data-ttu-id="ee243-116">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="ee243-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="ee243-117">és</span><span class="sxs-lookup"><span data-stu-id="ee243-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="ee243-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ee243-118">See Also</span></span>

- [<span data-ttu-id="ee243-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="ee243-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)