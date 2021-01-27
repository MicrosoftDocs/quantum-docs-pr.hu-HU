---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842927"
---
# <a name="squaresi-operation"></a><span data-ttu-id="250fe-102">SquareSI művelet</span><span class="sxs-lookup"><span data-stu-id="250fe-102">SquareSI operation</span></span>

<span data-ttu-id="250fe-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="250fe-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="250fe-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="250fe-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="250fe-105">Négyzetes aláírású egész szám `xs` , és a eredményét tárolja `result` , amelynek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="250fe-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="250fe-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="250fe-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="250fe-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="250fe-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="250fe-108">n bites egész szám – négyzet (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="250fe-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="250fe-109">eredmény: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="250fe-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="250fe-110">a 2n-bit result (SignedLittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="250fe-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="250fe-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="250fe-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="250fe-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="250fe-112">Remarks</span></span>

<span data-ttu-id="250fe-113">A megvalósítás a IntegerSquare-ra támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="250fe-113">The implementation relies on IntegerSquare.</span></span>