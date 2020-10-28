---
uid: Microsoft.Quantum.Canon.BoundA
title: Bounda függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716692"
---
# <a name="bounda-function"></a><span data-ttu-id="ef24e-102">Bounda függvény</span><span class="sxs-lookup"><span data-stu-id="ef24e-102">BoundA function</span></span>

<span data-ttu-id="ef24e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ef24e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ef24e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef24e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef24e-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="ef24e-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="ef24e-106">A módosító `A` azt jelzi, hogy a tömbben lévő összes művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="ef24e-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="ef24e-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ef24e-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="ef24e-108">műveletek: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) , adj []</span><span class="sxs-lookup"><span data-stu-id="ef24e-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="ef24e-109">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="ef24e-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="ef24e-110">Kimenet: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) : Adj</span><span class="sxs-lookup"><span data-stu-id="ef24e-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="ef24e-111">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="ef24e-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ef24e-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ef24e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ef24e-113">Nem</span><span class="sxs-lookup"><span data-stu-id="ef24e-113">'T</span></span>

<span data-ttu-id="ef24e-114">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="ef24e-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef24e-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ef24e-115">See Also</span></span>

- [<span data-ttu-id="ef24e-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="ef24e-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)