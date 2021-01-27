---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850443"
---
# <a name="applytotail-operation"></a><span data-ttu-id="b074f-102">ApplyToTail művelet</span><span class="sxs-lookup"><span data-stu-id="b074f-102">ApplyToTail operation</span></span>

<span data-ttu-id="b074f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b074f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b074f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b074f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b074f-105">Egy műveletet alkalmaz egy tömb utolsó elemére.</span><span class="sxs-lookup"><span data-stu-id="b074f-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b074f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b074f-106">Description</span></span>

<span data-ttu-id="b074f-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b074f-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b074f-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b074f-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="b074f-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b074f-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b074f-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="b074f-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b074f-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="b074f-111">targets : 'T[]</span></span>

<span data-ttu-id="b074f-112">A célok tömbje, amelyből az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="b074f-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b074f-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b074f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b074f-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b074f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b074f-115">Nem</span><span class="sxs-lookup"><span data-stu-id="b074f-115">'T</span></span>

<span data-ttu-id="b074f-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="b074f-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="b074f-117">Példa</span><span class="sxs-lookup"><span data-stu-id="b074f-117">Example</span></span>

<span data-ttu-id="b074f-118">A következő Q # kódrészletek egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="b074f-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="b074f-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b074f-119">See Also</span></span>

- [<span data-ttu-id="b074f-120">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="b074f-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="b074f-121">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="b074f-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="b074f-122">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="b074f-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)