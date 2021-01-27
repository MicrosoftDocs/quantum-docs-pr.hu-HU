---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850516"
---
# <a name="applytorest-operation"></a><span data-ttu-id="17e3b-102">ApplyToRest művelet</span><span class="sxs-lookup"><span data-stu-id="17e3b-102">ApplyToRest operation</span></span>

<span data-ttu-id="17e3b-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17e3b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17e3b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17e3b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17e3b-105">A művelet a tömb első elemére vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="17e3b-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="17e3b-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="17e3b-106">Description</span></span>

<span data-ttu-id="17e3b-107">A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="17e3b-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="17e3b-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="17e3b-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="17e3b-109">op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17e3b-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="17e3b-110">Egy alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="17e3b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="17e3b-111">célok: 'T []</span><span class="sxs-lookup"><span data-stu-id="17e3b-111">targets : 'T[]</span></span>

<span data-ttu-id="17e3b-112">A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .</span><span class="sxs-lookup"><span data-stu-id="17e3b-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17e3b-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17e3b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="17e3b-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="17e3b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17e3b-115">Nem</span><span class="sxs-lookup"><span data-stu-id="17e3b-115">'T</span></span>

<span data-ttu-id="17e3b-116">Az alkalmazni kívánt művelet bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="17e3b-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="17e3b-117">Példa</span><span class="sxs-lookup"><span data-stu-id="17e3b-117">Example</span></span>

<span data-ttu-id="17e3b-118">A következő Q # kódrészletek egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="17e3b-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="17e3b-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="17e3b-119">See Also</span></span>

- [<span data-ttu-id="17e3b-120">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="17e3b-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="17e3b-121">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="17e3b-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="17e3b-122">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="17e3b-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)