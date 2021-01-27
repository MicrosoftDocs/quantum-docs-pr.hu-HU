---
uid: Microsoft.Quantum.Arrays.Swapped
title: Felcserélt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850952"
---
# <a name="swapped-function"></a><span data-ttu-id="eb8c0-102">Felcserélt függvény</span><span class="sxs-lookup"><span data-stu-id="eb8c0-102">Swapped function</span></span>

<span data-ttu-id="eb8c0-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="eb8c0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="eb8c0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb8c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb8c0-105">Egy tömb két elemének kicserélt változatát alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="eb8c0-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="eb8c0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eb8c0-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="eb8c0-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb8c0-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb8c0-108">Az elsőként felcserélni kívánt elem indexe.</span><span class="sxs-lookup"><span data-stu-id="eb8c0-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="eb8c0-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb8c0-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb8c0-110">A felcserélni kívánt második elem indexe.</span><span class="sxs-lookup"><span data-stu-id="eb8c0-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="eb8c0-111">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="eb8c0-111">arr : 'T[]</span></span>

<span data-ttu-id="eb8c0-112">A felcserélni kívánt elemeket tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="eb8c0-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="eb8c0-113">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="eb8c0-113">Output : 'T[]</span></span>

<span data-ttu-id="eb8c0-114">Az a tömb, amelyben a helyszíni swap alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="eb8c0-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="eb8c0-115">Példa</span><span class="sxs-lookup"><span data-stu-id="eb8c0-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="eb8c0-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="eb8c0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb8c0-117">Nem</span><span class="sxs-lookup"><span data-stu-id="eb8c0-117">'T</span></span>

