---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842703"
---
# <a name="plusa-function"></a><span data-ttu-id="df3a4-102">Plusa függvény</span><span class="sxs-lookup"><span data-stu-id="df3a4-102">PlusA function</span></span>

<span data-ttu-id="df3a4-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="df3a4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="df3a4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df3a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df3a4-105">Két bemenet összegét (összefűzését) adja vissza.</span><span class="sxs-lookup"><span data-stu-id="df3a4-105">Returns the sum (concatenation) of two inputs.</span></span>

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a><span data-ttu-id="df3a4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df3a4-106">Input</span></span>

### <a name="a--element"></a><span data-ttu-id="df3a4-107">a: ' Element []</span><span class="sxs-lookup"><span data-stu-id="df3a4-107">a : 'Element[]</span></span>

<span data-ttu-id="df3a4-108">Az első bemenet $a $ összegezve.</span><span class="sxs-lookup"><span data-stu-id="df3a4-108">The first input $a$ to be summed.</span></span>


### <a name="b--element"></a><span data-ttu-id="df3a4-109">b: "elem []</span><span class="sxs-lookup"><span data-stu-id="df3a4-109">b : 'Element[]</span></span>

<span data-ttu-id="df3a4-110">A második bemenet $b $ összegezve.</span><span class="sxs-lookup"><span data-stu-id="df3a4-110">The second input $b$ to be summed.</span></span>



## <a name="output--element"></a><span data-ttu-id="df3a4-111">Kimenet: ' Element []</span><span class="sxs-lookup"><span data-stu-id="df3a4-111">Output : 'Element[]</span></span>

<span data-ttu-id="df3a4-112">Az összeg $a + b $.</span><span class="sxs-lookup"><span data-stu-id="df3a4-112">The sum $a + b$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="df3a4-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="df3a4-113">Type Parameters</span></span>

### <a name="element"></a><span data-ttu-id="df3a4-114">"Elem</span><span class="sxs-lookup"><span data-stu-id="df3a4-114">'Element</span></span>

<span data-ttu-id="df3a4-115">A két bemeneti tömb egyes elemeinek típusa.</span><span class="sxs-lookup"><span data-stu-id="df3a4-115">The type of each element in each of the two input arrays.</span></span>