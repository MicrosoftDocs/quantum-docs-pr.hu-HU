---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723207"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="22b76-102">BigFraction-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="22b76-102">BigFraction user defined type</span></span>

<span data-ttu-id="22b76-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="22b76-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="22b76-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22b76-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22b76-105">Az űrlap racionális számát jelöli `p/q` .</span><span class="sxs-lookup"><span data-stu-id="22b76-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="22b76-106">Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.</span><span class="sxs-lookup"><span data-stu-id="22b76-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="22b76-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="22b76-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="22b76-108">Számláló: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22b76-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22b76-109">A frakció számlálója.</span><span class="sxs-lookup"><span data-stu-id="22b76-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="22b76-110">Nevező: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22b76-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22b76-111">A frakció nevezője/</span><span class="sxs-lookup"><span data-stu-id="22b76-111">Denominator of the fraction/</span></span>