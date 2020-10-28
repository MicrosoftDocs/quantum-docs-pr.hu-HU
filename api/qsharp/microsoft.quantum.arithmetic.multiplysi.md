---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: MultiplySI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719752"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="4bf53-102">MultiplySI művelet</span><span class="sxs-lookup"><span data-stu-id="4bf53-102">MultiplySI operation</span></span>

<span data-ttu-id="4bf53-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4bf53-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4bf53-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bf53-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bf53-105">Az aláírt egész számot az aláírt egész számmal szorozza `xs` `ys` meg, és tárolja az eredményt a értékben `result` , amelynek nullának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="4bf53-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="4bf53-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4bf53-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="4bf53-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4bf53-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="4bf53-108">n bites multiplicand (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4bf53-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="4bf53-109">[SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="4bf53-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="4bf53-110">n bites szorzó (SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4bf53-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="4bf53-111">eredmény: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4bf53-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="4bf53-112">a 2n-bit result (SignedLittleEndian) értékének kezdetben a következő állapotban kell lennie: $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="4bf53-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4bf53-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4bf53-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

