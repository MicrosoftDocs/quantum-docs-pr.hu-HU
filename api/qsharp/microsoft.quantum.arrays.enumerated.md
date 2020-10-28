---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Enumerált függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719308"
---
# <a name="enumerated-function"></a><span data-ttu-id="01bdd-102">Enumerált függvény</span><span class="sxs-lookup"><span data-stu-id="01bdd-102">Enumerated function</span></span>

<span data-ttu-id="01bdd-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="01bdd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="01bdd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01bdd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01bdd-105">A tömbnek megfelelően egy új tömböt ad vissza, amely az eredeti tömb elemeit tartalmazza, valamint az egyes elemek indexeit.</span><span class="sxs-lookup"><span data-stu-id="01bdd-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="01bdd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="01bdd-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="01bdd-107">tömb: "táv []</span><span class="sxs-lookup"><span data-stu-id="01bdd-107">array : 'TElement[]</span></span>

<span data-ttu-id="01bdd-108">Egy tömb, amelynek elemeit enumerálni kell.</span><span class="sxs-lookup"><span data-stu-id="01bdd-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="01bdd-109">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int), "tele) []</span><span class="sxs-lookup"><span data-stu-id="01bdd-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="01bdd-110">Egy új tömb, amely az eredeti tömb elemeit tartalmazza az indexekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="01bdd-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="01bdd-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="01bdd-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="01bdd-112">"Táv</span><span class="sxs-lookup"><span data-stu-id="01bdd-112">'TElement</span></span>

<span data-ttu-id="01bdd-113">A tömb elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="01bdd-113">The type of elements of the array.</span></span>