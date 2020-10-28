---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721384"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="fe9fb-102">AssertMostSignificantBit művelet</span><span class="sxs-lookup"><span data-stu-id="fe9fb-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="fe9fb-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fe9fb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fe9fb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe9fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe9fb-105">Azt állítja be, hogy egy qubit-regiszter legjelentősebb qubit, amely egy előjel nélküli egész számot jelöl, egy adott állapotban van.</span><span class="sxs-lookup"><span data-stu-id="fe9fb-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="fe9fb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fe9fb-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="fe9fb-107">érték: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="fe9fb-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="fe9fb-108">Az érvényesített legmagasabb bit értéke.</span><span class="sxs-lookup"><span data-stu-id="fe9fb-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="fe9fb-109">szám: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe9fb-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fe9fb-110">Előjel nélküli egész szám, amelynek a legmagasabb bit be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="fe9fb-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe9fb-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe9fb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe9fb-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fe9fb-112">Remarks</span></span>

<span data-ttu-id="fe9fb-113">A művelet ellenőrzött verziója figyelmen kívül hagyja a vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="fe9fb-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe9fb-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="fe9fb-114">See Also</span></span>

- [<span data-ttu-id="fe9fb-115">Microsoft. Quantum. belső. érvényesítés</span><span class="sxs-lookup"><span data-stu-id="fe9fb-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)