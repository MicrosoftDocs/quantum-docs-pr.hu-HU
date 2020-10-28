---
uid: Microsoft.Quantum.Arithmetic.AddI
title: További művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721685"
---
# <a name="addi-operation"></a><span data-ttu-id="191c1-102">További művelet</span><span class="sxs-lookup"><span data-stu-id="191c1-102">AddI operation</span></span>

<span data-ttu-id="191c1-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="191c1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="191c1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="191c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="191c1-105">A a regisztráció méretétől függően automatikusan kiválasztja a carry és a nélkül lehetőséget a hozzáadáshoz `ys` .</span><span class="sxs-lookup"><span data-stu-id="191c1-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="191c1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="191c1-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="191c1-107">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="191c1-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="191c1-108">$n $ bites addend.</span><span class="sxs-lookup"><span data-stu-id="191c1-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="191c1-109">[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :</span><span class="sxs-lookup"><span data-stu-id="191c1-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="191c1-110">Addend legalább $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="191c1-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="191c1-111">Az eredményt fogja tárolni.</span><span class="sxs-lookup"><span data-stu-id="191c1-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="191c1-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="191c1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

