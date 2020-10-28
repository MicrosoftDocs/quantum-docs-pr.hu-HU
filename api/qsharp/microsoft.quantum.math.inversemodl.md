---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723627"
---
# <a name="inversemodl-function"></a><span data-ttu-id="acdca-102">InverseModL függvény</span><span class="sxs-lookup"><span data-stu-id="acdca-102">InverseModL function</span></span>

<span data-ttu-id="acdca-103">Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="acdca-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="acdca-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="acdca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="acdca-105">$B $ értéket ad vissza, amely $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="acdca-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="acdca-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="acdca-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="acdca-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="acdca-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="acdca-108">Az invertált szám</span><span class="sxs-lookup"><span data-stu-id="acdca-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="acdca-109">modulus: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="acdca-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="acdca-110">Az a modulus, amely szerint a számok invertálva vannak</span><span class="sxs-lookup"><span data-stu-id="acdca-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="acdca-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="acdca-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="acdca-112">Egész $b $, például $a \cdot b = 1 (\operatorname{mod} \texttt{modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="acdca-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>