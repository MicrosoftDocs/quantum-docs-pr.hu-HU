---
uid: Microsoft.Quantum.Math.ModL
title: ModL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723108"
---
# <a name="modl-function"></a><span data-ttu-id="68718-102">ModL függvény</span><span class="sxs-lookup"><span data-stu-id="68718-102">ModL function</span></span>

<span data-ttu-id="68718-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="68718-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="68718-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="68718-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="68718-105">Egy szám modulusát adja vissza egy másik számra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="68718-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="68718-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="68718-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="68718-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68718-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="68718-108">A bemeneti $a $, amelynek a modulusát vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="68718-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="68718-109">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68718-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="68718-110">Az a szám, amelynek a $a $ értékét vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="68718-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="68718-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="68718-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="68718-112">A modulus $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="68718-112">The modulus $a \bmod b$.</span></span>