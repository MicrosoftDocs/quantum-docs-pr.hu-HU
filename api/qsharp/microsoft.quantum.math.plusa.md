---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194831"
---
# <a name="plusa-function"></a><span data-ttu-id="ec1cc-102">Plusa függvény</span><span class="sxs-lookup"><span data-stu-id="ec1cc-102">PlusA function</span></span>

<span data-ttu-id="ec1cc-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="ec1cc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="ec1cc-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec1cc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec1cc-105">Két bemenet összegét (összefűzését) adja vissza.</span><span class="sxs-lookup"><span data-stu-id="ec1cc-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="ec1cc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ec1cc-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="ec1cc-107">a: ' Element []</span><span class="sxs-lookup"><span data-stu-id="ec1cc-107">a : 'Element[]</span></span>

<span data-ttu-id="ec1cc-108">Az első bemenet $a $ összegezve.</span><span class="sxs-lookup"><span data-stu-id="ec1cc-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="ec1cc-109">b: "elem []</span><span class="sxs-lookup"><span data-stu-id="ec1cc-109">b : 'Element[]</span></span>

<span data-ttu-id="ec1cc-110">A második bemenet $b $ összegezve.</span><span class="sxs-lookup"><span data-stu-id="ec1cc-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="ec1cc-111">Kimenet: ' Element []</span><span class="sxs-lookup"><span data-stu-id="ec1cc-111">Output : 'Element[]</span></span>

<span data-ttu-id="ec1cc-112">Az összeg $a + b $.</span><span class="sxs-lookup"><span data-stu-id="ec1cc-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ec1cc-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ec1cc-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="ec1cc-114">"Elem</span><span class="sxs-lookup"><span data-stu-id="ec1cc-114">'Element</span></span>

<span data-ttu-id="ec1cc-115">A két bemeneti tömb egyes elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="ec1cc-115">The type of each element in each of the two input arrays.</span></span>