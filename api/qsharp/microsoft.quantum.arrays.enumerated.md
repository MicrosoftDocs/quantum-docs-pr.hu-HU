---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Enumerált függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221419"
---
# <a name="enumerated-function"></a><span data-ttu-id="249bc-102">Enumerált függvény</span><span class="sxs-lookup"><span data-stu-id="249bc-102">Enumerated function</span></span>

<span data-ttu-id="249bc-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="249bc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="249bc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="249bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="249bc-105">A tömbnek megfelelően egy új tömböt ad vissza, amely az eredeti tömb elemeit tartalmazza, valamint az egyes elemek indexeit.</span><span class="sxs-lookup"><span data-stu-id="249bc-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="249bc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="249bc-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="249bc-107">tömb: "táv []</span><span class="sxs-lookup"><span data-stu-id="249bc-107">array : 'TElement[]</span></span>

<span data-ttu-id="249bc-108">Egy tömb, amelynek elemeit enumerálni kell.</span><span class="sxs-lookup"><span data-stu-id="249bc-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="249bc-109">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int), "tele) []</span><span class="sxs-lookup"><span data-stu-id="249bc-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="249bc-110">Egy új tömb, amely az eredeti tömb elemeit tartalmazza az indexekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="249bc-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="249bc-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="249bc-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="249bc-112">"Táv</span><span class="sxs-lookup"><span data-stu-id="249bc-112">'TElement</span></span>

<span data-ttu-id="249bc-113">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="249bc-113">The type of elements of the array.</span></span>