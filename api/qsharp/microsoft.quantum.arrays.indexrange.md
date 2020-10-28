---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719152"
---
# <a name="indexrange-function"></a><span data-ttu-id="f9916-102">IndexRange függvény</span><span class="sxs-lookup"><span data-stu-id="f9916-102">IndexRange function</span></span>

<span data-ttu-id="f9916-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9916-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9916-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9916-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9916-105">Egy tömb esetében az adott tömb indexei között egy tartományt ad vissza, amely a for ciklusban használható.</span><span class="sxs-lookup"><span data-stu-id="f9916-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="f9916-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f9916-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="f9916-107">tömb: "táv []</span><span class="sxs-lookup"><span data-stu-id="f9916-107">array : 'TElement[]</span></span>

<span data-ttu-id="f9916-108">Olyan tömb, amelynek vissza kell adni az indexek tartományát.</span><span class="sxs-lookup"><span data-stu-id="f9916-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="f9916-109">Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f9916-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f9916-110">Egy tartomány az összes indexben a tömbben.</span><span class="sxs-lookup"><span data-stu-id="f9916-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f9916-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f9916-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="f9916-112">"Táv</span><span class="sxs-lookup"><span data-stu-id="f9916-112">'TElement</span></span>

<span data-ttu-id="f9916-113">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="f9916-113">The type of elements of the array.</span></span>