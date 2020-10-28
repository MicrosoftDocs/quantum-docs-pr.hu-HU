---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709608"
---
# <a name="plusa-function"></a><span data-ttu-id="c2827-102">Plusa függvény</span><span class="sxs-lookup"><span data-stu-id="c2827-102">PlusA function</span></span>

<span data-ttu-id="c2827-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c2827-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c2827-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2827-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2827-105">Két bemenet összegét (összefűzését) adja vissza.</span><span class="sxs-lookup"><span data-stu-id="c2827-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="c2827-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c2827-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="c2827-107">a: ' Element []</span><span class="sxs-lookup"><span data-stu-id="c2827-107">a : 'Element[]</span></span>

<span data-ttu-id="c2827-108">Az első bemenet $a $ összegezve.</span><span class="sxs-lookup"><span data-stu-id="c2827-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="c2827-109">b: "elem []</span><span class="sxs-lookup"><span data-stu-id="c2827-109">b : 'Element[]</span></span>

<span data-ttu-id="c2827-110">A második bemenet $b $ összegezve.</span><span class="sxs-lookup"><span data-stu-id="c2827-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="c2827-111">Kimenet: ' Element []</span><span class="sxs-lookup"><span data-stu-id="c2827-111">Output : 'Element[]</span></span>

<span data-ttu-id="c2827-112">Az összeg $a + b $.</span><span class="sxs-lookup"><span data-stu-id="c2827-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c2827-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c2827-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="c2827-114">"Elem</span><span class="sxs-lookup"><span data-stu-id="c2827-114">'Element</span></span>

<span data-ttu-id="c2827-115">A két bemeneti tömb egyes elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="c2827-115">The type of each element in each of the two input arrays.</span></span>