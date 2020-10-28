---
uid: Microsoft.Quantum.Math.Fraction
title: A felhasználó által megadott típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723655"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="d47e1-102">A felhasználó által megadott típus</span><span class="sxs-lookup"><span data-stu-id="d47e1-102">Fraction user defined type</span></span>

<span data-ttu-id="d47e1-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d47e1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d47e1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d47e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d47e1-105">Az űrlap racionális számát jelöli `p/q` .</span><span class="sxs-lookup"><span data-stu-id="d47e1-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="d47e1-106">Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.</span><span class="sxs-lookup"><span data-stu-id="d47e1-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="d47e1-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="d47e1-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="d47e1-108">Számláló: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d47e1-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d47e1-109">A frakció számlálója.</span><span class="sxs-lookup"><span data-stu-id="d47e1-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="d47e1-110">Nevező: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d47e1-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d47e1-111">A frakció nevezője/</span><span class="sxs-lookup"><span data-stu-id="d47e1-111">Denominator of the fraction/</span></span>