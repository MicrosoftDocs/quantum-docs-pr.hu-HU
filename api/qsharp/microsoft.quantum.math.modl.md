---
uid: Microsoft.Quantum.Math.ModL
title: ModL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846836"
---
# <a name="modl-function"></a><span data-ttu-id="e925f-102">ModL függvény</span><span class="sxs-lookup"><span data-stu-id="e925f-102">ModL function</span></span>

<span data-ttu-id="e925f-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e925f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e925f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e925f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e925f-105">Egy szám modulusát adja vissza egy másik számra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="e925f-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="e925f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e925f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e925f-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e925f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e925f-108">A bemeneti $a $, amelynek a modulusát vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="e925f-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e925f-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e925f-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e925f-110">Az a szám, amelynek a $a $ értékét vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="e925f-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e925f-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e925f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e925f-112">A modulus $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="e925f-112">The modulus $a \bmod b$.</span></span>