---
uid: Microsoft.Quantum.Arithmetic.Invert2sSI
title: Invert2sSI művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Invert2sSI
qsharp.summary: Inverts a given integer modulo 2's complement.
ms.openlocfilehash: e86a5f8586cf438189c19da75c60cfd97632dcb1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843136"
---
# <a name="invert2ssi-operation"></a><span data-ttu-id="8ac9c-102">Invert2sSI művelet</span><span class="sxs-lookup"><span data-stu-id="8ac9c-102">Invert2sSI operation</span></span>

<span data-ttu-id="8ac9c-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8ac9c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8ac9c-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8ac9c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8ac9c-105">Egy adott egész szám, a 2. adatosztási modul kiegészítését fordította.</span><span class="sxs-lookup"><span data-stu-id="8ac9c-105">Inverts a given integer modulo 2's complement.</span></span>

```qsharp
operation Invert2sSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8ac9c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8ac9c-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="8ac9c-107">xs: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8ac9c-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="8ac9c-108">az n bites előjeles egész szám (SignedLittleEndian) nem lesz lefordítva a 2. adatosztások kiegészítéseként.</span><span class="sxs-lookup"><span data-stu-id="8ac9c-108">n-bit signed integer (SignedLittleEndian), will be inverted modulo 2's complement.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ac9c-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ac9c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

