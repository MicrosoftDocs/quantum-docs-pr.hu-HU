---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850591"
---
# <a name="applytomost-operation"></a><span data-ttu-id="96e19-102">ApplyToMost művelet</span><span class="sxs-lookup"><span data-stu-id="96e19-102">ApplyToMost operation</span></span>

<span data-ttu-id="96e19-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="96e19-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="96e19-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96e19-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96e19-105">Egy művelet egy tömb utolsó elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="96e19-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="96e19-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="96e19-106">Description</span></span>

<span data-ttu-id="96e19-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="96e19-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="96e19-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="96e19-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="96e19-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96e19-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="96e19-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="96e19-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="96e19-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="96e19-111">targets : 'T[]</span></span>

<span data-ttu-id="96e19-112">A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="96e19-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96e19-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96e19-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96e19-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="96e19-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96e19-115">Nem</span><span class="sxs-lookup"><span data-stu-id="96e19-115">'T</span></span>

<span data-ttu-id="96e19-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="96e19-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="96e19-117">Példa</span><span class="sxs-lookup"><span data-stu-id="96e19-117">Example</span></span>

<span data-ttu-id="96e19-118">A következő Q # kódrészletek egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="96e19-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="96e19-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="96e19-119">See Also</span></span>

- [<span data-ttu-id="96e19-120">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="96e19-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="96e19-121">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="96e19-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="96e19-122">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="96e19-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)