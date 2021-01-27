---
uid: Microsoft.Quantum.Canon.Bound
title: Kötött függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841054"
---
# <a name="bound-function"></a><span data-ttu-id="86632-102">Kötött függvény</span><span class="sxs-lookup"><span data-stu-id="86632-102">Bound function</span></span>

<span data-ttu-id="86632-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="86632-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="86632-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86632-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86632-105">Egy adott bemeneten alapuló műveletek tömbje egy olyan új műveletet hoz létre, amely az egyes műveleteket a sorban hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="86632-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="86632-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="86632-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="86632-107">műveletek: nem => [egység](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="86632-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="86632-108">Egy adott bemeneten végrehajtandó műveletek sora.</span><span class="sxs-lookup"><span data-stu-id="86632-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="86632-109">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86632-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="86632-110">Egy új művelet, amely az adott műveletet a bemenetén belül hajtja végre.</span><span class="sxs-lookup"><span data-stu-id="86632-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="86632-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="86632-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="86632-112">Nem</span><span class="sxs-lookup"><span data-stu-id="86632-112">'T</span></span>

<span data-ttu-id="86632-113">Az a cél, amelybe a tömbben szereplő műveletek mindegyike működik.</span><span class="sxs-lookup"><span data-stu-id="86632-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="86632-114">Példa</span><span class="sxs-lookup"><span data-stu-id="86632-114">Example</span></span>

<span data-ttu-id="86632-115">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="86632-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="86632-116">és</span><span class="sxs-lookup"><span data-stu-id="86632-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="86632-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="86632-117">See Also</span></span>

- [<span data-ttu-id="86632-118">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="86632-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="86632-119">Microsoft. Quantum. Canon. Bounda</span><span class="sxs-lookup"><span data-stu-id="86632-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="86632-120">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="86632-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)