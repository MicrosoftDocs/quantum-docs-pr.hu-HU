---
uid: Microsoft.Quantum.Canon.Delayed
title: Késleltetett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716258"
---
# <a name="delayed-function"></a><span data-ttu-id="ca361-102">Késleltetett függvény</span><span class="sxs-lookup"><span data-stu-id="ca361-102">Delayed function</span></span>

<span data-ttu-id="ca361-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca361-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca361-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca361-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca361-105">Egy olyan műveletet ad vissza, amely a megadott argumentummal megadott műveletet alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="ca361-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="ca361-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ca361-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="ca361-107">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="ca361-107">op : 'T => 'U</span></span> 

<span data-ttu-id="ca361-108">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="ca361-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="ca361-109">ARG: nem</span><span class="sxs-lookup"><span data-stu-id="ca361-109">arg : 'T</span></span>

<span data-ttu-id="ca361-110">Az a bemenet, amelyre a művelet vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="ca361-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="ca361-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit) => U</span><span class="sxs-lookup"><span data-stu-id="ca361-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="ca361-112">Egy új művelet, amely `op` a bemenetre vonatkozik `arg`</span><span class="sxs-lookup"><span data-stu-id="ca361-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ca361-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ca361-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca361-114">Nem</span><span class="sxs-lookup"><span data-stu-id="ca361-114">'T</span></span>

<span data-ttu-id="ca361-115">A késleltetni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="ca361-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="ca361-116">' U</span><span class="sxs-lookup"><span data-stu-id="ca361-116">'U</span></span>

<span data-ttu-id="ca361-117">A késleltetni kívánt művelet visszatérési típusa.</span><span class="sxs-lookup"><span data-stu-id="ca361-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca361-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ca361-118">See Also</span></span>

- [<span data-ttu-id="ca361-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="ca361-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="ca361-120">Microsoft. Quantum. Canon. késleltetett</span><span class="sxs-lookup"><span data-stu-id="ca361-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="ca361-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="ca361-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="ca361-122">Microsoft. Quantum. Canon. delay</span><span class="sxs-lookup"><span data-stu-id="ca361-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)