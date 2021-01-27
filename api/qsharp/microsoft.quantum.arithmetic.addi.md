---
uid: Microsoft.Quantum.Arithmetic.AddI
title: További művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843850"
---
# <a name="addi-operation"></a><span data-ttu-id="52da9-102">További művelet</span><span class="sxs-lookup"><span data-stu-id="52da9-102">AddI operation</span></span>

<span data-ttu-id="52da9-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="52da9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="52da9-104">Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="52da9-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="52da9-105">A a regisztráció méretétől függően automatikusan kiválasztja a carry és a nélkül lehetőséget a hozzáadáshoz `ys` .</span><span class="sxs-lookup"><span data-stu-id="52da9-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="52da9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="52da9-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="52da9-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="52da9-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="52da9-108">$n $ bites addend.</span><span class="sxs-lookup"><span data-stu-id="52da9-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="52da9-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="52da9-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="52da9-110">Addend legalább $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="52da9-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="52da9-111">Az eredményt fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="52da9-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52da9-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52da9-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

