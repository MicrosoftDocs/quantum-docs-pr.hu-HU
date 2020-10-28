---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Invert2sSI művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: 6cb27477d66320ba741eb902e7c8a9e740a9b3f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721037"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="a9a2c-102">Invert2sSI művelet</span><span class="sxs-lookup"><span data-stu-id="a9a2c-102">Invert2sSI operation</span></span>

<span data-ttu-id="a9a2c-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a9a2c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a9a2c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9a2c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9a2c-105">Egy adott egész szám, a 2. adatosztási modul kiegészítését fordította.</span><span class="sxs-lookup"><span data-stu-id="a9a2c-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="a9a2c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a9a2c-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="a9a2c-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a9a2c-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="a9a2c-108">az n bites előjeles egész szám (SignedLittleEndian) nem lesz lefordítva a 2. adatosztások kiegészítéseként.</span><span class="sxs-lookup"><span data-stu-id="a9a2c-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a9a2c-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a9a2c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

