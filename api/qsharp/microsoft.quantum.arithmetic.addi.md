---
uid: Microsoft.Quantum.Arithmetic.AddI
title: További művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191023"
---
# <a name="addi-operation"></a><span data-ttu-id="a71a2-102">További művelet</span><span class="sxs-lookup"><span data-stu-id="a71a2-102">AddI operation</span></span>

<span data-ttu-id="a71a2-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a71a2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a71a2-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a71a2-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a71a2-105">A a regisztráció méretétől függően automatikusan kiválasztja a carry és a nélkül lehetőséget a hozzáadáshoz `ys` .</span><span class="sxs-lookup"><span data-stu-id="a71a2-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a71a2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a71a2-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="a71a2-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a71a2-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a71a2-108">$n $ bites addend.</span><span class="sxs-lookup"><span data-stu-id="a71a2-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="a71a2-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="a71a2-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a71a2-110">Addend legalább $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="a71a2-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="a71a2-111">Az eredményt fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="a71a2-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a71a2-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a71a2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

