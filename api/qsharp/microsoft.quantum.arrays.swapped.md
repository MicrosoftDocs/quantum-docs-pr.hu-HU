---
uid: Microsoft.Quantum.Arrays.Swapped
title: Felcserélt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718828"
---
# <a name="swapped-function"></a><span data-ttu-id="39f8f-102">Felcserélt függvény</span><span class="sxs-lookup"><span data-stu-id="39f8f-102">Swapped function</span></span>

<span data-ttu-id="39f8f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39f8f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39f8f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39f8f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39f8f-105">Egy tömb két elemének kicserélt változatát alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="39f8f-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="39f8f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="39f8f-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="39f8f-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39f8f-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39f8f-108">Az elsőként felcserélni kívánt elem indexe.</span><span class="sxs-lookup"><span data-stu-id="39f8f-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="39f8f-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39f8f-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39f8f-110">A felcserélni kívánt második elem indexe.</span><span class="sxs-lookup"><span data-stu-id="39f8f-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="39f8f-111">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="39f8f-111">arr : 'T[]</span></span>

<span data-ttu-id="39f8f-112">A felcserélni kívánt elemeket tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="39f8f-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="39f8f-113">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="39f8f-113">Output : 'T[]</span></span>

<span data-ttu-id="39f8f-114">Az a tömb, amelyben a helyszíni swap alkalmazva van.</span><span class="sxs-lookup"><span data-stu-id="39f8f-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="39f8f-115">Példa</span><span class="sxs-lookup"><span data-stu-id="39f8f-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="39f8f-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="39f8f-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39f8f-117">Nem</span><span class="sxs-lookup"><span data-stu-id="39f8f-117">'T</span></span>

