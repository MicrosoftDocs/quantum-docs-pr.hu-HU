---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846904"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="963e8-102">BigFraction-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="963e8-102">BigFraction user defined type</span></span>

<span data-ttu-id="963e8-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="963e8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="963e8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="963e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="963e8-105">Az űrlap racionális számát jelöli `p/q` .</span><span class="sxs-lookup"><span data-stu-id="963e8-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="963e8-106">Az egész szám a `p` rekord első eleme, `q` amely a rekord második eleme.</span><span class="sxs-lookup"><span data-stu-id="963e8-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="963e8-107">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="963e8-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="963e8-108">Számláló: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="963e8-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="963e8-109">A frakció számlálója.</span><span class="sxs-lookup"><span data-stu-id="963e8-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="963e8-110">Nevező: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="963e8-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="963e8-111">A frakció nevezője/</span><span class="sxs-lookup"><span data-stu-id="963e8-111">Denominator of the fraction/</span></span>