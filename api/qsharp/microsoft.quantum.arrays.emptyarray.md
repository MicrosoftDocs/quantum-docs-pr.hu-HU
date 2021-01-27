---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846176"
---
# <a name="emptyarray-function"></a><span data-ttu-id="bdf53-102">EmptyArray függvény</span><span class="sxs-lookup"><span data-stu-id="bdf53-102">EmptyArray function</span></span>

<span data-ttu-id="bdf53-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bdf53-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bdf53-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bdf53-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bdf53-105">Egy adott típus üres tömbjét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="bdf53-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="bdf53-106">Kimenet: "táv []</span><span class="sxs-lookup"><span data-stu-id="bdf53-106">Output : 'TElement[]</span></span>

<span data-ttu-id="bdf53-107">Az üres tömb.</span><span class="sxs-lookup"><span data-stu-id="bdf53-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bdf53-108">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="bdf53-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="bdf53-109">"Táv</span><span class="sxs-lookup"><span data-stu-id="bdf53-109">'TElement</span></span>

<span data-ttu-id="bdf53-110">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="bdf53-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="bdf53-111">Példa</span><span class="sxs-lookup"><span data-stu-id="bdf53-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```