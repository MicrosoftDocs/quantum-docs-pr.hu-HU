---
uid: Microsoft.Quantum.Canon.Bound
title: Kötött függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716706"
---
# <a name="bound-function"></a><span data-ttu-id="49481-102">Kötött függvény</span><span class="sxs-lookup"><span data-stu-id="49481-102">Bound function</span></span>

<span data-ttu-id="49481-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="49481-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="49481-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49481-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49481-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="49481-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="49481-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="49481-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="49481-107">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="49481-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="49481-108">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="49481-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="49481-109">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49481-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="49481-110">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="49481-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="49481-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="49481-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="49481-112">Nem</span><span class="sxs-lookup"><span data-stu-id="49481-112">'T</span></span>

<span data-ttu-id="49481-113">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="49481-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="49481-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="49481-114">See Also</span></span>

- [<span data-ttu-id="49481-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="49481-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="49481-116">Microsoft. Quantum. Canon. Bounda</span><span class="sxs-lookup"><span data-stu-id="49481-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="49481-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="49481-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)