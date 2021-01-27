---
uid: Microsoft.Quantum.Math.Fraction
title: A felhasználó által megadott típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857518"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="9673d-102">A felhasználó által megadott típus</span><span class="sxs-lookup"><span data-stu-id="9673d-102">Fraction user defined type</span></span>

<span data-ttu-id="9673d-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="9673d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="9673d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9673d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9673d-105">Az űrlap racionális számát jelöli `p/q` .</span><span class="sxs-lookup"><span data-stu-id="9673d-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="9673d-106">Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.</span><span class="sxs-lookup"><span data-stu-id="9673d-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="9673d-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="9673d-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="9673d-108">Számláló: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9673d-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9673d-109">A frakció számlálója.</span><span class="sxs-lookup"><span data-stu-id="9673d-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="9673d-110">Nevező: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9673d-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9673d-111">A frakció nevezője/</span><span class="sxs-lookup"><span data-stu-id="9673d-111">Denominator of the fraction/</span></span>