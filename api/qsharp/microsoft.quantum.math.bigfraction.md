---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211083"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="66c82-102">BigFraction-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="66c82-102">BigFraction user defined type</span></span>

<span data-ttu-id="66c82-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="66c82-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="66c82-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66c82-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66c82-105">Az űrlap racionális számát jelöli `p/q` .</span><span class="sxs-lookup"><span data-stu-id="66c82-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="66c82-106">Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.</span><span class="sxs-lookup"><span data-stu-id="66c82-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="66c82-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="66c82-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="66c82-108">Számláló: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="66c82-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="66c82-109">A frakció számlálója.</span><span class="sxs-lookup"><span data-stu-id="66c82-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="66c82-110">Nevező: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="66c82-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="66c82-111">A frakció nevezője/</span><span class="sxs-lookup"><span data-stu-id="66c82-111">Denominator of the fraction/</span></span>