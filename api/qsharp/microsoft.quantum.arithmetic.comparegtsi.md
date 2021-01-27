---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846695"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="9544a-102">CompareGTSI művelet</span><span class="sxs-lookup"><span data-stu-id="9544a-102">CompareGTSI operation</span></span>

<span data-ttu-id="9544a-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9544a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9544a-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9544a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9544a-105">A burkoló az aláírt egész szám összehasonlításához: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="9544a-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9544a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9544a-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="9544a-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9544a-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="9544a-108">Első $n $ bites szám</span><span class="sxs-lookup"><span data-stu-id="9544a-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="9544a-109">[SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="9544a-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="9544a-110">Második $n $ bites szám</span><span class="sxs-lookup"><span data-stu-id="9544a-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="9544a-111">eredmény: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9544a-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9544a-112">Akkor lesz felfordítva, ha $xs ></span><span class="sxs-lookup"><span data-stu-id="9544a-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="9544a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9544a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

