---
uid: Microsoft.Quantum.Math.Fraction
title: A felhasználó által megadott típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210675"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="0af18-102">A felhasználó által megadott típus</span><span class="sxs-lookup"><span data-stu-id="0af18-102">Fraction user defined type</span></span>

<span data-ttu-id="0af18-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0af18-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0af18-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0af18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0af18-105">Az űrlap racionális számát jelöli `p/q` .</span><span class="sxs-lookup"><span data-stu-id="0af18-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="0af18-106">Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.</span><span class="sxs-lookup"><span data-stu-id="0af18-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="0af18-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="0af18-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="0af18-108">Számláló: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0af18-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0af18-109">A frakció számlálója.</span><span class="sxs-lookup"><span data-stu-id="0af18-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="0af18-110">Nevező: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0af18-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0af18-111">A frakció nevezője/</span><span class="sxs-lookup"><span data-stu-id="0af18-111">Denominator of the fraction/</span></span>