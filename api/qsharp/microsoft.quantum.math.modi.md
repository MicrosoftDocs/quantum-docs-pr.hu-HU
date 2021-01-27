---
uid: Microsoft.Quantum.Math.ModI
title: ModI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModI
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 8f4ff37767e5120b99834a63ed19055ba1806907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848063"
---
# <a name="modi-function"></a><span data-ttu-id="98c43-102">ModI függvény</span><span class="sxs-lookup"><span data-stu-id="98c43-102">ModI function</span></span>

<span data-ttu-id="98c43-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="98c43-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="98c43-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98c43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98c43-105">Egy szám modulusát adja vissza egy másik számra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="98c43-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="98c43-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="98c43-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="98c43-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98c43-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98c43-108">A bemeneti $a $, amelynek a modulusát vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="98c43-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--int"></a><span data-ttu-id="98c43-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98c43-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98c43-110">Az a szám, amelynek a $a $ értékét vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="98c43-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="98c43-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98c43-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98c43-112">A modulus $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="98c43-112">The modulus $a \bmod b$.</span></span>