---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Invert2sSI művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: 86d90fc5406089549de0036fcaebd9dc9d188c40
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222847"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="4e037-102">Invert2sSI művelet</span><span class="sxs-lookup"><span data-stu-id="4e037-102">Invert2sSI operation</span></span>

<span data-ttu-id="4e037-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4e037-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4e037-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4e037-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4e037-105">Egy adott egész szám, a 2. adatosztási modul kiegészítését fordította.</span><span class="sxs-lookup"><span data-stu-id="4e037-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4e037-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4e037-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="4e037-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4e037-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="4e037-108">az n bites előjeles egész szám (SignedLittleEndian) nem lesz lefordítva a 2. adatosztások kiegészítéseként.</span><span class="sxs-lookup"><span data-stu-id="4e037-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4e037-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e037-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

