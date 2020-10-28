---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: c8c4e3cca001aa6d7ce1b9df106ce77f74524301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719536"
---
# <a name="squaresi-operation"></a><span data-ttu-id="dafc5-102">SquareSI művelet</span><span class="sxs-lookup"><span data-stu-id="dafc5-102">SquareSI operation</span></span>

<span data-ttu-id="dafc5-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dafc5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dafc5-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dafc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dafc5-105">Négyzetes aláírású egész szám `xs` , és a eredményét tárolja `result` , amelynek kezdetben nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="dafc5-105">Square signed integer `xs` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="dafc5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dafc5-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="dafc5-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dafc5-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="dafc5-108">n bites egész szám – négyzet (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dafc5-108">n-bit integer to square (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="dafc5-109">eredmény: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dafc5-109">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="dafc5-110">a 2n-bit result (SignedLittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="dafc5-110">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dafc5-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dafc5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dafc5-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="dafc5-112">Remarks</span></span>

<span data-ttu-id="dafc5-113">A megvalósítás a IntegerSquare-ra támaszkodik.</span><span class="sxs-lookup"><span data-stu-id="dafc5-113">The implementation relies on IntegerSquare.</span></span>