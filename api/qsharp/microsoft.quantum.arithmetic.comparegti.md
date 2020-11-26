---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: CompareGTI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223476"
---
# <a name="comparegti-operation"></a><span data-ttu-id="227d3-102">CompareGTI művelet</span><span class="sxs-lookup"><span data-stu-id="227d3-102">CompareGTI operation</span></span>

<span data-ttu-id="227d3-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="227d3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="227d3-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="227d3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="227d3-105">Burkoló az egész szám összehasonlításához: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="227d3-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="227d3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="227d3-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="227d3-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="227d3-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="227d3-108">Első $n $ bites szám</span><span class="sxs-lookup"><span data-stu-id="227d3-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="227d3-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="227d3-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="227d3-110">Második $n $ bites szám</span><span class="sxs-lookup"><span data-stu-id="227d3-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="227d3-111">eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="227d3-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="227d3-112">Akkor lesz felfordítva, ha $x > y $</span><span class="sxs-lookup"><span data-stu-id="227d3-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="227d3-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="227d3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

