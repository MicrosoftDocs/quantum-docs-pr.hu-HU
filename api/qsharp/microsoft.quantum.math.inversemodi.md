---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723640"
---
# <a name="inversemodi-function"></a><span data-ttu-id="d8ba0-102">InverseModI függvény</span><span class="sxs-lookup"><span data-stu-id="d8ba0-102">InverseModI function</span></span>

<span data-ttu-id="d8ba0-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d8ba0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d8ba0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8ba0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8ba0-105">$B $ értéket ad vissza, amely $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="d8ba0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d8ba0-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="d8ba0-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8ba0-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8ba0-108">Az invertált szám</span><span class="sxs-lookup"><span data-stu-id="d8ba0-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="d8ba0-109">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8ba0-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8ba0-110">Az a modulus, amely szerint a számok invertálva vannak</span><span class="sxs-lookup"><span data-stu-id="d8ba0-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="d8ba0-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8ba0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8ba0-112">Egész $b $, például $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="d8ba0-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>