---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223493"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="c3baf-102">CompareGTSI művelet</span><span class="sxs-lookup"><span data-stu-id="c3baf-102">CompareGTSI operation</span></span>

<span data-ttu-id="c3baf-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c3baf-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c3baf-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c3baf-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c3baf-105">A burkoló az aláírt egész szám összehasonlításához: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="c3baf-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c3baf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c3baf-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="c3baf-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c3baf-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c3baf-108">Első $n $ bites szám</span><span class="sxs-lookup"><span data-stu-id="c3baf-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="c3baf-109">[SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="c3baf-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="c3baf-110">Második $n $ bites szám</span><span class="sxs-lookup"><span data-stu-id="c3baf-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="c3baf-111">eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c3baf-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c3baf-112">Akkor lesz felfordítva, ha $xs ></span><span class="sxs-lookup"><span data-stu-id="c3baf-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3baf-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3baf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

