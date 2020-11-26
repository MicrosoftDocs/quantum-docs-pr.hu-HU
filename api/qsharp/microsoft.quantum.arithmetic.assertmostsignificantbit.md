---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223782"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="81cc0-102">AssertMostSignificantBit művelet</span><span class="sxs-lookup"><span data-stu-id="81cc0-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="81cc0-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="81cc0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="81cc0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="81cc0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="81cc0-105">Azt állítja be, hogy egy qubit-regiszter legjelentősebb qubit, amely egy előjel nélküli egész számot jelöl, egy adott állapotban van.</span><span class="sxs-lookup"><span data-stu-id="81cc0-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="81cc0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="81cc0-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="81cc0-107">érték: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="81cc0-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="81cc0-108">Az érvényesített legmagasabb bit értéke.</span><span class="sxs-lookup"><span data-stu-id="81cc0-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="81cc0-109">szám: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81cc0-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81cc0-110">Előjel nélküli egész szám, amelynek a legmagasabb bit be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="81cc0-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81cc0-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81cc0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="81cc0-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="81cc0-112">Remarks</span></span>

<span data-ttu-id="81cc0-113">A művelet ellenőrzött verziója figyelmen kívül hagyja a vezérlőket.</span><span class="sxs-lookup"><span data-stu-id="81cc0-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="81cc0-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="81cc0-114">See Also</span></span>

- [<span data-ttu-id="81cc0-115">Microsoft. Quantum. belső. érvényesítés</span><span class="sxs-lookup"><span data-stu-id="81cc0-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)