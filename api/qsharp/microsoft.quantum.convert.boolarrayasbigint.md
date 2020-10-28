---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713613"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="e51f6-102">BoolArrayAsBigInt függvény</span><span class="sxs-lookup"><span data-stu-id="e51f6-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="e51f6-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e51f6-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e51f6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e51f6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e51f6-105">Logikai értékek adott tömbjét konvertálja egy egyenértékű nagy egész számra.</span><span class="sxs-lookup"><span data-stu-id="e51f6-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="e51f6-106">A tömb 0 eleme a legkevesebb nagy egész szám.</span><span class="sxs-lookup"><span data-stu-id="e51f6-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="e51f6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e51f6-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="e51f6-108">a: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e51f6-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="e51f6-109">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e51f6-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="e51f6-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e51f6-110">Remarks</span></span>

<span data-ttu-id="e51f6-111">További részleteket a [C# BigInteger konstruktorában](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) talál.</span><span class="sxs-lookup"><span data-stu-id="e51f6-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>